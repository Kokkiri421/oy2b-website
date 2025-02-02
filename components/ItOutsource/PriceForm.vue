<template>
  <div class="price">
    <div class="price__top-text">
      <slot name="top-text"></slot>
    </div>
    <div class="form-container" ref="order">
      <div class="form-container__top">
        <h4 class="name-phone-company-form__header">
          Давайте прямо сейчас рассчитаем стоимость работ
        </h4>
      </div>

      <p class="form-error-message" v-if="errors.length > 0">
        Заполните обязательные поля
      </p>
      <p class="form-success-message" v-else-if="success">
        Заявка успешно отправлена
      </p>
      <form class="name-phone-company-form" @submit="checkForm">
        <pretty-input
          :name="'name'"
          :placeholder="'Имя'"
          class="name-phone-company-form__item"
          :value="name"
          @onInput="setName"
          :error="errors.includes('name')"
        ></pretty-input>
        <pretty-input
          :name="'phone'"
          :type="'tel'"
          :placeholder="'Телефон'"
          class="name-phone-company-form__item"
          :value="phone"
          @onInput="setPhone"
          :error="errors.includes('phone')"
        ></pretty-input>
        <pretty-input
          :name="'company'"
          :placeholder="'Компания'"
          class="name-phone-company-form__item"
          :value="company"
          @onInput="setCompany"
          :error="errors.includes('company')"
        ></pretty-input>
        <div class="name-phone-company-form__item">
          <button class="dialog-button" :disabled="success">
            <div class="shining-button"></div>
            Отправить
          </button>
        </div>
      </form>
      <div class="price__privacy">
        <NuxtLink to="/privacy/">политика конфиденциальности</NuxtLink>
      </div>
    </div>
    <div class="price__bottom-text">
      <slot name="bottom-text"></slot>
    </div>
  </div>
</template>

<script>
import PrettyInput from '~/components/Common/PrettyInput'

export default {
  data() {
    return {
      name: '',
      phone: '',
      company: '',
      success: false,
      errors: [],
    }
  },
  components: {
    PrettyInput,
  },

  methods: {
    async checkForm(e) {
      e.preventDefault()
      if (this.success) return
      this.errors = []
      let phone = this.phone
        .replace('+7(', '')
        .replace(')', '')
        .replace('-', '')
        .replace('-', '')
      if (!this.name) {
        this.errors.push('name')
      }
      if (!this.phone || phone.length !== 10) {
        this.errors.push('phone')
      }
      if (!this.company) {
        this.errors.push('company')
      }
      if (this.errors.length === 0) {
        let fullname = this.name.split(' ')
        let routename = this.$store.state.routeNames[this.$route.path]
        let body = {
          dev: process.env.APP_ENV === 'dev',
          contact: {
            name: fullname[0],
            surname: fullname[1] || '.',
            phones: [{ phone: phone }],
          },
          description: `Тип формы: ${routename}. Рассчёт стоимости работ\nКомпания или адрес: ${this.company}\n`,
        }
        let gtmName = this.$store.state.gtmNames[this.$route.path]
        let response = await this.$axios
          .post(process.env.CRM_LINK, body)
          .then(() => dataLayer.push({ event: gtmName }))
          .finally(
            async () =>
              await this.$axios
                .post(process.env.BOT_LINK, body)
                .then(async () => {
                  await this.setSuccess()
                  this.phone = ''
                  this.company = ''
                  this.name = ''
                })
          )
        return true
      }
    },
    setName(e) {
      this.name = e.target.value
    },
    setPhone(e) {
      this.phone = e.target.value
    },
    setCompany(e) {
      this.company = e.target.value
    },
    setSuccess() {
      this.success = true
      setTimeout(() => (this.success = false), 5000)
    },
  },
}
</script>

<style lang="scss" scoped>
@import '~/assets/media_mixin';
@import '~/assets/colors';

.price {
  .article {
    line-height: 1.62em;
    color: #999;
    @include _700() {
      font-size: 0.9em;
    }
  }

  .form-container {
    background-color: $light-blue-color;
    border-radius: 6px;
    padding: 1em;
    //margin: 3em 0;
    @include _650 {
    }
    &__top {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
    }
    .name-phone-company-form {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      margin-bottom: 1em;
      &__header {
        max-width: calc(100% - 150px - 1em);
        @include _650() {
          max-width: 100%;
        }
      }

      &__error {
        border-color: $red-color1 !important;
      }

      &__item {
        vertical-align: top;
        margin: 0 1em 0 0;
        width: calc(25% - 0.75em);
        @include _1000() {
          display: block;
          margin: 0 0 1em;
          width: 100%;
        }

        button {
          width: 100%;
        }

        &:nth-last-child(-n + 1) {
          margin: 0;
        }
      }

      @include _1000() {
        flex-direction: column;
      }
    }
  }

  &__privacy {
    color: #fff;
    font-size: 0.6em;
    line-height: 1.4em;

    a {
      color: $text-color;
      transition: color 0.3s ease-out;

      &:hover {
        color: $red-color1;
      }
    }
  }
  .image-container {
    height: 100%;
    width: 150px;
    position: relative;
    .image {
      position: absolute;
      width: 125px;
      height: 110px;
      bottom: -45px;
      left: 10px;
    }
    @include _650() {
      display: none;
    }
  }
}
</style>
