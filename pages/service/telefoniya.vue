<template>
  <div class="container">
    <hero-block :is-anchor="true" @onClick="scrollToServices">
      <template v-slot:header> Виртуальная телефония </template>
      <template v-slot:description>
        <div class="description">
          <p class="article">
            Современный инструмент для ведения бизнеса. <br />
            Гибкая АТС, которую легко и просто обслуживать. <br />
            Эффективная коммуникация с удаленными сотрудниками. <br />
            <span class="dn-600">
              Оптимальные цены на междугородние и международные звонки. <br />
              Более 65 базовых функций. <br />
              Не думайте об обслуживании Телефонии — занимайтесь бизнесом.
            </span>
          </p>
        </div>
      </template>
      <template v-slot:form-prefix>
        Проверьте возможность подключения сервисов и услуг:
      </template>
    </hero-block>
    <div class="page-content">
      <div class="wrapper">
        <h4 class="service-list-header">
          4 причины выбрать телефонию от Oyster Telecom
        </h4>
        <service-list class="page-content-block" ref="next-page">
          <service-block :background-color="'#ff7a00'" :type="'block'">
            <template v-slot:header> Сокращение затрат </template>
            <template v-slot:description>
              <p class="article">
                Телефония от Oyster Telecom создана специально для сокращения
                затрат бизнеса.
              </p>
              <ul class="article">
                <li class="article">
                  Минимальная стоимость приобретения по сравнению с аналогичными
                  решениями
                </li>

                <li class="article">Бесплатные звонки между сотрудниками</li>
                <li class="article">Бесплатные межофисные коммуникации</li>
                <li class="article">
                  Оптимизация работы за счет интеграции телефонии в CRM
                </li>
                <li class="article">
                  Повышение эффективности за счет вебклиента и приложений на iOS
                  и Android
                </li>
                <li class="article">Сокращение расходов на связь до 70%</li>
              </ul>
            </template>
            <template v-slot:button
              ><button class="dialog-button">Заказать</button>
            </template>
          </service-block>
          <service-block
            :background-color="'#ff7a00'"
            :type="'block'"
            :is-grey="true"
          >
            <template v-slot:header> Интеграция с CRM </template>
            <template v-slot:description>
              <p class="article">
                Интеграция в вашу систему CRM поможет менеджеру узнать, кто ему
                звонит, еще до того, как он ответит. Карточка клиента
                автоматически откроется при входящем вызове - вы увидите, когда
                он звонил в последний раз и с каким сотрудником разговаривал. Вы
                обслужите больше обращений, закроете больше сделок и получите
                лояльных клиентов!
              </p>
              <ul class="article">
                <li class="article">Звоните прямо из CRM</li>
                <li class="article">
                  Входящие звонки с новых номеров автоматически создают новые
                  карточки клиентов
                </li>
                <li class="article">
                  Автоматическое ведение истории вызовов без ручного ввода
                </li>
                <li class="article">
                  Автоматически запрашивайте номер клиента при обращении
                </li>
                <li class="article">
                  Маршрутизируйте обращения на основе номера или запроса
                </li>
                <li class="article">Формируйте и совершайте обзвон клиентов</li>
                <li class="article">
                  Прослушивайте звонки сотрудников для оценки эффективности
                </li>
              </ul>
              <p class="article privacy">
                * Данная услуга предоставляется проектным клиентам
              </p>
            </template>
            <template v-slot:button
              ><button class="dialog-button">Заказать</button>
            </template>
          </service-block>
          <service-block
            :background-color="'#ff7a00'"
            :type="'block'"
            :is-grey="true"
          >
            <template v-slot:header> Простая установка и управление </template>
            <template v-slot:description>
              <ul>
                <li class="article">
                  Установка как в облаке так и на локальном сервере, тонких
                  клиентах, Raspberry Pi
                </li>
                <li class="article">
                  Автоматические подключение и настройка телефонов и VoIP шлюзов
                </li>
                <li class="article">Совместимость с большинством аппаратов</li>
                <li class="article">
                  Возможности удаленной настройки и перезагрузки
                </li>
                <li class="article">Нативный интерфейс управления АТС</li>
                <li class="article">
                  Автоматическая установка обновлений. Легкая масштабируемость
                </li>
                <li class="article">Приложение на IOS и Android</li>
              </ul>
            </template>
            <template v-slot:button
              ><button class="dialog-button">Заказать</button>
            </template>
          </service-block>
          <service-block :background-color="'#ff7a00'" :type="'block'">
            <template v-slot:header> Мобильность </template>
            <template v-slot:description>
              <ul class="article">
                <li class="article">
                  Современные мобильные приложения на IOS и Android
                </li>

                <li class="article">Унифицированный клиент для браузера</li>
                <li class="article">
                  Одновременный вызов в приложение и телефон
                </li>
                <li class="article">
                  Бесплатные интегрированные видеоконференции
                </li>
                <li class="article">Корпоративный чат</li>
                <li class="article">
                  Интеграция чата с клиентом на сайт и Facebook
                </li>
                <li class="article">Удаленная настройка через QR-код</li>
                <li class="article">Полностью защищенная голосовая связь</li>
              </ul>
            </template>
            <template v-slot:button
              ><button class="dialog-button">Заказать</button>
            </template>
          </service-block>
        </service-list>
        <div class="optimal-solution">
          <h4>Выберите оптимальное решение для вашего бизнеса</h4>
          <p class="article">
            Не нужно докупать дополнительные модули, дорогие аппаратные
            расширения и разбираться в запутанном лицензировании. Три понятных
            набора функций– одна мощная система бизнес-телефонии.
          </p>
        </div>

        <telephony-table class="telephony-table" v-if="isVisibleTable"></telephony-table>
        <p class="service-message page-content-block">
          <icon :icon-name="'rouble-icon'" class="icon">
            <rouble-icon />
          </icon>
          <span
            >- стоимость услуги не входит в стоимость тарифа и рассчитывается
            отдельно. Свяжитесь с менеджером, чтобы узнать подробности</span
          >
        </p>
        <special-price class="page-content-block" :background-color="'#ff7a00'"
          ><template v-slot:text
            ><span
              >При подключении 10 линий вы получаете
              <strong>25 Мбит/с интернета совершенно бесплатно</strong></span
            ></template
          ></special-price
        >

        <div class="sla page-content-block">
          <sla-block class="page-content-block" />
        </div>
        <div class="page-content-block">
          <h4 class="header">Наши эксперты</h4>
          <p class="article">
            В Oyster Telecom работают технические специалисты с&nbsp;релевантным
            опытом из&nbsp;различных технических сфер услуг для&nbsp;бизнеса.
          </p>
        </div>
        <call-us-block class="page-content-block" />
        <price-form class="page-content-block"></price-form>
        <div class="bottom-text">
          <h5>
            Мы создаем лучшее решение для&nbsp;качественной связи компании
            с&nbsp; клиентами и эффективного взаимодействия между сотрудниками.
          </h5>
          <p class="article">
            Специалисты Oyster Telecom знают, как необходима в офисе налаженная
            и функциональная телефонная связь, а также знают, как ее установить!
            Мы создадим для вас бизнес-инструмент для оптимизации, статистики и
            аналитики. Влезем в код, изменим конфигурацию, интегрируем с вашими
            CRM и ERP, даже если они самописные. Подхватим вас на любом этапе
            модернизации: заменим старые АТС на виртуальные, поможем подключить
            к мини-АТС платы SIP-телефонии, подключим по SIPtrunk вашу новую
            облачную АТС.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HeroBlock from '~/components/Common/HeroBlock'
import ServiceBlock from '~/components/Common/ServiceBlock'
import ServiceList from '~/components/Common/ServiceList'
import QuestionBlock from '~/components/Common/QuestionBlock'
import TelephonyTable from '~/components/Telephony/TelephonyTable'
import RoubleIcon from '~/components/Icons/RoubleIcon'
import Icon from '~/components/Icons/Icon'
import SpecialPrice from '~/components/Common/SpecialPrice'
import SlaBlock from '~/components/ItOutsource/SlaBlock'
import CallUsBlock from '~/components/Index/CallUsBlock'
import PriceForm from '~/components/ItOutsource/PriceForm'

export default {
  data() {
    return {
      isVisibleTable : false,
    }
  },
  head() {
    return {
      title: 'IP-телефония для бизнеса в Санкт-Петербурге',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:
            'Заказать услуги ip-телефонии для бизнеса от компании Oyster Telecom в Санкт-Петербурге. Предлагаем ip-телефонию, виртуальную АТС, sip-телефонию подключение за 3 дня! Оставляйте заявку!',
        },
      ],
    }
  },
  components: {
    HeroBlock,
    ServiceBlock,
    ServiceList,
    QuestionBlock,
    TelephonyTable,
    RoubleIcon,
    Icon,
    SpecialPrice,
    SlaBlock,
    CallUsBlock,
    PriceForm,
  },

  methods: {
    showTable: function() {
      this.isVisibleTable = true;
    },
    scrollToServices: function () {
      window.scrollTo({
        top:
          this.$refs['next-page'].$el.getBoundingClientRect().top +
          window.pageYOffset -
          100,
        behavior: 'smooth',
      })
    },
    scrollToOrder: function () {
      window.scrollTo({
        top:
          this.$refs['question'].$refs['order'].getBoundingClientRect().top +
          window.pageYOffset -
          100,
        behavior: 'smooth',
      })
    },
  },
  mounted() {
    setTimeout(() => {
      this.showTable()
    }, 100);
  },
  beforeDestroy() {
    
  },
  
}
</script>

<style lang="scss" scoped>
@import '~/assets/media_mixin';

.icon {
  width: 1.25em;
  height: 1.25em;
  vertical-align: middle;
}
.container {
  display: flex;
  flex-direction: column;
}
.fw800 {
  font-weight: 600;
}

.optimal-solution {
  margin-bottom: 1em;
}
.telephony-table {
  margin-bottom: 1em;
}
.privacy {
  font-size: 0.8em;
  color: #00000085;

  @include _600() {
    font-size: 0.7em;
  }
}
</style>
