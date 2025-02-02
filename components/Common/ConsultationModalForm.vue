<template>
  <div class="modal-form">
    <h4>Обсудить проект</h4>
    <p class="form-error-message" v-if="errors.length > 0">
      Заполните обязательные поля
    </p>
    <p class="form-success-message" v-else-if="success">
      Заявка успешно отправлена
    </p>
    <form @submit="checkForm">
      <pretty-input
        :name="'name'"
        :placeholder="'Ваше Имя'"
        class="modal-form__item"
        :value="name"
        @onInput="setName"
        :error="errors.includes('name')"
      ></pretty-input>
      <pretty-input
        :type="'tel'"
        :name="'phone'"
        :placeholder="'Телефон'"
        class="modal-form__item"
        :value="phone"
        @onInput="setPhone"
        :error="errors.includes('phone')"
      ></pretty-input>
      <div class="radio-buttons">
        <div class="modal-form__radio">
          <input
            id="ip"
            name="radio"
            type="radio"
            :checked="type === 'ip'"
            @change="
              () => {
                type = 'ip'
              }
            "
          />
          <label for="ip" class="radio-label">ИП</label>
        </div>
        <div class="modal-form__radio">
          <input
            id="ul"
            name="radio"
            type="radio"
            :checked="type === 'ul'"
            @change="
              () => {
                type = 'ul'
              }
            "
          />
          <label for="ul" class="radio-label">Юр.лицо</label>
        </div>
      </div>
      <button class="dialog-button modal-form__button" :disabled="success">
        Обсудить проект
      </button>
    </form>
    <div class="modal-form__privacy">
      <NuxtLink class="link" to="/privacy/"
        >политика конфиденциальности</NuxtLink
      >
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
      type: 'ip',
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
          description: `Тип формы: ${
            routename || 'Другая форма (Компания, SLA или проч.)'
          }. Обсудить проект\nТип клиента: ${
            this.type === 'ip' ? 'ИП' : 'Юр. Лицо'
          }\n`,
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
    setSuccess() {
      this.success = true
      setTimeout(() => (this.success = false), 5000)
    },
  },
}
</script>

<style lang="scss" scoped>
@import '~/assets/media_mixin';
.modal-form {
  padding: 1em;
  max-width: 650px;
  box-sizing: border-box;
  &__item {
    border: 1px solid #ccc;
    border-radius: 4px;
    width: 100%;
    margin-bottom: 1em;
  }
  $color1: #fff;
  $color2: #d81428;
  &__radio {
    position: relative;
    margin: 0.5rem;
    input[type='radio'] {
      position: absolute;
      opacity: 0;
      left: -30px;
      z-index: 2;
      width: 100%;
      height: 100%;
      + .radio-label {
        margin-right: 30px;
        &:before {
          content: '';
          position: absolute;
          left: -30px;
          width: 20px;
          height: 20px;
          border-radius: 100%;
          border: 1px solid #dfdfdf;
          transition: border-color 0.2s ease-out;
          z-index: 1;
        }
        &::after {
          content: '';
          position: absolute;
          left: -25px;
          top: 5px;
          width: 12px;
          height: 12px;
          border-radius: 100%;

          transition: border-color 0.2s ease-out;
          z-index: 1;
        }
      }
      &:checked {
        + .radio-label {
          &:before {
            //background-color: $color2;
            border-radius: 100%;
            //box-shadow: inset 0 0 0 6px $color1;
          }
          &:after {
            background-color: $color2;
          }
        }
      }
      &:focus {
        + .radio-label {
          &:before {
            outline: none;
            border-color: $color2;
          }
        }
      }
      &:disabled {
        + .radio-label {
          &:before {
            box-shadow: inset 0 0 0 4px $color1;
            border-color: darken($color1, 25%);
            background: darken($color1, 25%);
          }
        }
      }
      + .radio-label {
        &:empty {
          &:before {
            margin-right: 0;
          }
        }
      }
    }
  }
  &__button {
    width: 100%;
    margin-top: 1em;
    margin-bottom: 0.5em;
  }
  &__privacy {
    font-size: 0.6em;
    line-height: 1.4em;
    color: #000;
    .link {
      color: #000;
      transition: color 0.3s ease-out;
      &:hover {
        color: #d81428;
      }
    }
  }
  .radio-buttons {
    display: flex;
    flex-direction: row;
    padding-left: 1.5em;
  }
}
</style>
