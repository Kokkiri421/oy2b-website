<template>
  <div class="wrapper">
    <div class="vacancies">
      <div class="page-content">
        <h1>Вакансии</h1>
        <div class="page-content-block vacancies-info">
          <div class="vacancies-info__text">
            <p class="article">
              Мы команда единомышленников, братство молодых и активных людей,
              добивающихся поставленных целей и предлагающих своим клиентам
              первоклассный современный сервис.
            </p>
            <p class="article">
              Работа в Oyster Telecom - это не только возможность стать
              специалистом в сфере телекоммуникаций, но и реальный шанс
              осуществить амбициозные и авангардные IT проекты.
            </p>
            <p class="article">
              Сделай правильный выбор - стань частью Oyster Telecom!
            </p>
            <div class="vacancy">
              <h5 class="header vacancy__header" @click="changeExpanded(0)">
                <span
                  class="header-content"
                  :class="{ rotateIcon: expanded[0] }"
                  >Ведущий инженер отдела подключений</span
                >
              </h5>
              <div
                class="vacancy__info page-content-block"
                :class="{ show: expanded[0] }"
              >
                <h5 class="header">Обязанности:</h5>
                <ul class="article">
                  <li>
                    Обработка внутренних заявок по реализации схем подключений
                    типовых услуг связи и проектных задач;
                  </li>
                  <li>
                    Выполнение работ по подключению услуг связи: интернет,
                    телефония, WiFi, видеонаблюдение;
                  </li>
                  <li>Обнаружение и устранение неполадок в линейной части;</li>
                  <li>Проведение работ по сервисным заявкам</li>
                </ul>
                <h5 class="header">Требования:</h5>
                <ul class="article">
                  <li>
                    Ответственность, коммуникабельность, пунктуальность,
                    обучаемость;
                  </li>
                  <li>Понимание технологий связи;</li>
                  <li>Понимание процесса подключения услуги связи;</li>
                  <li>Готовность к разъездной работе</li>
                </ul>
                <h5 class="header">Будут вашими преимуществами</h5>
                <ul class="article">
                  <li>Опыт работы в сферах ИТ и телекоммуникаций;</li>
                  <li>Опыт настройки сетевого оборудования</li>
                </ul>
                <h5 class="header">Условия:</h5>
                <ul class="article">
                  <li>Оформление по ТК РФ;</li>
                  <li>Режим работы: ПН-ПТ с 10:00 до 19:00;</li>
                  <li>Социальный пакет;</li>
                  <li>Обучение, тренинги.</li>
                  <li>
                    Премирование по качественным показателям и за участие в
                    проектах
                  </li>
                </ul>
                <h5 class="header">Преимущества работы в нашей компании:</h5>
                <ul class="article">
                  <li>
                    Работа в молодом, активном, профессиональном коллективе;
                  </li>
                  <li>Возможности карьерного и профессионального развития;</li>
                  <li>
                    Интересные проекты, возможность работать с новыми продуктами
                    и технологиями в сфере телекоммуникаций;
                  </li>
                  <li>
                    Компания обладает техническими возможностями выполнять
                    большие объемы работ и реализовывать коммерческие проекты
                    высокой сложности (высокий профессионализм инженерного
                    состава, собственная волоконно-оптическая сеть с мощной
                    разветвленной структурой, широкая линейка продуктов,
                    практика вывода на рынок инновационных продуктов и решений).
                  </li>
                </ul>
                <button
                  class="dialog-button vacancy__apply"
                  @click="showModal('Ведущий инженер отдела подключений')"
                >
                  Откликнуться на вакансию
                </button>
              </div>
            </div>
            <div class="vacancy">
              <h5 class="header vacancy__header" @click="changeExpanded(1)">
                <span
                  class="header-content"
                  :class="{ rotateIcon: expanded[1] }"
                  >Менеджер по работе с клиентами</span
                >
              </h5>
              <div
                class="vacancy__info page-content-block"
                :class="{ show: expanded[1] }"
              >
                <h5 class="header">Обязанности:</h5>
                <ul class="article">
                  <li>Консультирование существующих клиентов;</li>
                  <li>
                    Создание и подбор оптимальных условий сотрудничества для
                    каждого клиента;
                  </li>
                  <li>Повторные и допродажи существующей базе клиентов;</li>
                  <li>Работа с оттоком;</li>
                  <li>
                    Разъяснительная работа и разрешение конфликтных ситуаций с
                    клиентами;
                  </li>
                  <li>
                    Организация и проведение телефонных переговоров и встреч с
                    первыми лицами компаний;
                  </li>
                  <li>Заключение и сопровождение договоров;</li>
                  <li>
                    Контроль исполнения обязательств по договорам на всех этапах
                    сотрудничества;
                  </li>
                  <li>Составление отчетности.</li>
                </ul>
                <h5 class="header">Требования:</h5>
                <ul class="article">
                  <li>Опыт продаж и сопровождения клиентов в B2B;</li>
                  <li>Высокие коммуникативные навыки;</li>
                  <li>Опыт проведения телефонных переговоров;</li>
                  <li>Способность работать в режиме многозначности;</li>
                  <li>Навыки сопровождения проектов;</li>
                  <li>Стремление к профессиональному и личностному росту;</li>
                  <li>Образование не ниже среднего;</li>
                  <li>Желание стать частью продуктивной команды.</li>
                </ul>
                <h5 class="header">Условия:</h5>
                <ul class="article">
                  <li>
                    Заработная плата обсуждается с успешным кандидатом и зависит
                    от навыков, умений и опыта;
                  </li>
                  <li>Оформление согласно ТК РФ;</li>
                  <li>График 5/2 с 9 до 18;</li>
                  <li>Премии и бонусы;</li>
                  <li>
                    Возможность прохождения профильных курсов и семинаров за
                    счет работодателя.
                  </li>
                </ul>
                <p class="article">Испытательный срок - 2 месяца</p>
                <h5 class="header">Преимущества работы в нашей компании:</h5>
                <ul class="article">
                  <li>
                    Работа в молодом, активном, профессиональном коллективе;
                  </li>
                  <li>Возможности карьерного и профессионального развития;</li>
                  <li>
                    Интересные проекты, возможность работать с новыми продуктами
                    и технологиями в сфере телекоммуникаций;
                  </li>
                  <li>
                    Компания обладает техническими возможностями выполнять
                    большие объемы работ и реализовывать коммерческие проекты
                    высокой сложности (высокий профессионализм инженерного
                    состава, собственная волоконно-оптическая сеть с мощной
                    разветвленной структурой, широкая линейка продуктов,
                    практика вывода на рынок инновационных продуктов и решений).
                  </li>
                </ul>
                <button
                  class="dialog-button vacancy__apply"
                  @click="showModal('Менеджер по работе с клиентами')"
                >
                  Откликнуться на вакансию
                </button>
              </div>
            </div>
            <div class="vacancy">
              <h5 class="header vacancy__header" @click="changeExpanded(2)">
                <span
                  class="header-content"
                  :class="{ rotateIcon: expanded[2] }"
                  >Менеджер по работе с бизнес - центрами</span
                >
              </h5>
              <div
                class="vacancy__info page-content-block"
                :class="{ show: expanded[2] }"
              >
                <h5 class="header">Обязанности:</h5>
                <ul class="article">
                  <li>
                    Выстраивание партнерских отношений с администрациями
                    бизнес-центров;
                  </li>
                  <li>Поиск и подключение бизнес-центров;</li>
                  <li>
                    Проведение акций и расширение клиентской базы на
                    подключенных объектах;
                  </li>
                  <li>Формирование отчетности о проведенной работе.</li>
                </ul>
                <h5 class="header">Требования:</h5>
                <ul class="article">
                  <li>Опыт активных продаж (В2В);</li>
                  <li>Навыки эффективных переговоров;</li>
                  <li>
                    Аналитический склад ума и умение находить оптимальное
                    комплексное решение для клиента;
                  </li>
                  <li>
                    Результативность, активность, профессионализм, интерес к
                    развитию инновационных технологий и творческий подход в
                    работе.
                  </li>
                </ul>
                <h5 class="header">Условия:</h5>
                <ul class="article">
                  <li>Условия работы и оформление согласно ТК РФ;</li>
                  <li>Пятидневка с 9:00 до 18:00, в пятницу до 17:00;</li>
                  <li>
                    Офис в 5-ти минутах от ст.м. Сенная, Садовая, Спасская;
                  </li>
                  <li>Прозрачная система премирования.</li>
                  <li>
                    Возможность прохождения профильных курсов и семинаров за
                    счет работодателя.
                  </li>
                </ul>
                <h5 class="header">Материальные преимущества:</h5>
                <ul class="article">
                  <li>
                    Уровень дохода при выполнении плановых показателей от 47 500
                    руб./мес.;
                  </li>
                  <li>Премия за подключение новых объектов</li>
                  <li>
                    Компенсационный пакет: оплата проезда, мобильной связи,
                    питания;
                  </li>
                  <li>
                    Развитие профессиональных и личных качеств в тренинг
                    агентстве за счет компании;
                  </li>
                  <li>
                    Для кандидатов с опытом работы на рынке телекоммуникаций или
                    коммерческой недвижимости - специальное предложение.
                  </li>
                  <li>
                    Совокупный доход зависит от индивидуальной результативности
                    и не ограничен "верхней планкой".
                  </li>
                </ul>
                <h5 class="header">Преимущества работы в нашей компании:</h5>
                <ul class="article">
                  <li>
                    Работа в молодом, активном, профессиональном коллективе;
                  </li>
                  <li>Возможности карьерного и профессионального развития;</li>
                  <li>
                    Интересные проекты, возможность работать с новыми продуктами
                    и технологиями в сфере телекоммуникаций;
                  </li>
                  <li>
                    Компания обладает техническими возможностями выполнять
                    большие объемы работ и реализовывать коммерческие проекты
                    высокой сложности (высокий профессионализм инженерного
                    состава, собственная волоконно-оптическая сеть с мощной
                    разветвленной структурой, широкая линейка продуктов,
                    практика вывода на рынок инновационных продуктов и решений).
                  </li>
                </ul>
                <button
                  class="dialog-button vacancy__apply"
                  @click="showModal('Менеджер по работе с бизнес - центрами')"
                >
                  Откликнуться на вакансию
                </button>
              </div>
            </div>
            <div class="vacancy">
              <h5 class="header vacancy__header" @click="changeExpanded(3)">
                <span
                  class="header-content"
                  :class="{ rotateIcon: expanded[3] }"
                  >Менеджер по рекламе и маркетингу</span
                >
              </h5>
              <div
                class="vacancy__info page-content-block"
                :class="{ show: expanded[3] }"
              >
                <h5 class="header">Требуемый опыт работы: 1–3 года</h5>
                <h5 class="header">Обязанности:</h5>
                <ul class="article">
                  <li>Разработка и заказ рекламной продукции</li>
                  <li>Разработка и создание полиграфии</li>
                  <li>Ведение соцсетей компании</li>
                  <li>Поддержка работы интернет-сайта компании</li>
                  <li>Мониторинг рекламы на объектах</li>
                  <li>Поиск исполнителей и подрядчиков</li>
                  <li>Ведение документооборота с бартерными клиентами</li>
                  <li>Ведение документооборота с ивентами</li>
                  <li>Ведение договоров по заказам отдела рекламы</li>
                  <li>
                    Анализ конкурентов, сбор информации о рекламных компаниях
                    конкурентов
                  </li>
                  <li>Участие в разработках рекламных концепций</li>
                  <li>Организация и проведение корпоративных мероприятий</li>
                </ul>
                <h5 class="header">Требования:</h5>
                <ul class="article">
                  <li>Опыт сопровождения существующих клиентов</li>
                  <li>Навыки работы в графических программах</li>
                  <li>
                    Опыт эффективной работы с контекстной рекламой, SMM,
                    таргетированной и медийной рекламой.
                  </li>
                  <li>
                    Понимание принципов SEO-оптимизации и SEO-продвижения.
                  </li>
                  <li>
                    Опыт работы с системами Web-аналитики: Google, Yandex и
                    сквозной аналитики.
                  </li>
                  <li>
                    Понимание UX-дизайна, опыт в тестировании сайтов, элементов
                    сайта и УТП.
                  </li>
                  <li>
                    Способность работать в режиме многозадачности над
                    несколькими проектами одновременно, навыки проектного
                    управления.
                  </li>
                  <li>
                    Опыт работы в B2B компании либо в компании провайдере связи
                    приветствуется
                  </li>
                </ul>
                <h5 class="header">Условия:</h5>
                <ul class="article">
                  <li>
                    Заработная плата обсуждается с успешным кандидатом и зависит
                    от опыта, навыков и умений
                  </li>
                  <li>Гибкий график</li>
                  <li>Оформление согласно ТК РФ</li>
                  <li>Офис в центре города м.Садовая</li>
                  <li>Рабочий день с 10:00 до 18:30</li>
                  <li>Испытательный срок 2 месяца</li>
                  <li>
                    Возможность прохождения профильных курсов и семинаров за
                    счет работодателя
                  </li>
                </ul>
                <button
                  class="dialog-button vacancy__apply"
                  @click="showModal('Менеджер по рекламе и маркетингу')"
                >
                  Откликнуться на вакансию
                </button>
              </div>
            </div>
            <div class="vacancy">
              <h5 class="header vacancy__header" @click="changeExpanded(4)">
                <span
                  class="header-content"
                  :class="{ rotateIcon: expanded[4] }"
                  >Менеджер корпоративных продаж</span
                >
              </h5>
              <div
                class="vacancy__info page-content-block"
                :class="{ show: expanded[4] }"
              >
                <p class="article">
                  <i
                    >На данный момент вакансия закрыта, но если ваше желание
                    стать частью команды Oyster Telecom от этого не стало меньше
                    - заполняйте форму и мы обязательно рассмотрим вашу
                    кандидатуру</i
                  >
                </p>
                <button
                  class="dialog-button vacancy__apply"
                  @click="showModal('Менеджер корпоративных продаж')"
                >
                  Откликнуться на вакансию
                </button>
              </div>
            </div>
            <div class="vacancy">
              <h5 class="header vacancy__header" @click="changeExpanded(5)">
                <span
                  class="header-content"
                  :class="{ rotateIcon: expanded[5] }"
                  >Технолог по строительству кабельных сетей</span
                >
              </h5>
              <div
                class="vacancy__info page-content-block"
                :class="{ show: expanded[5] }"
              >
                <p class="article">
                  <i
                    >На данный момент вакансия закрыта, но если ваше желание
                    стать частью команды Oyster Telecom от этого не стало меньше
                    - заполняйте форму и мы обязательно рассмотрим вашу
                    кандидатуру</i
                  >
                </p>
                <button
                  class="dialog-button vacancy__apply"
                  @click="
                    showModal('Технолог по строительству кабельных сетей')
                  "
                >
                  Откликнуться на вакансию
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <modal-window :show="isModalShown" @onClick="showModal"
      ><vacancy-apply-modal-form
        @onClick="showModal"
        :vacancy-name="vacancyName"
    /></modal-window>
    <div class="header-bg"></div>
  </div>
</template>

<script>
import ModalWindow from '~/components/Common/ModalWindow'
import VacancyApplyModalForm from '~/components/Vacancies/VacancyApplyModalForm.vue'
export default {
  head() {
    return {
      title: 'Вакансии Oyster Telecom',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Информация о провайдере Oyster Telecom.',
        },
      ],
    }
  },
  data() {
    return {
      expanded: Array(6).fill(false),
      isModalShown: false,
      vacancyName: '',
    }
  },
  components: {
    ModalWindow,
    VacancyApplyModalForm,
  },
  computed: {
    activeMenuStatus: function () {
      return this.isActiveNavigationMenu
    },
  },

  methods: {
    changeExpanded: function (index) {
      this.$set(this.expanded, index, !this.expanded[index])
    },
    showModal(name = '') {
      this.vacancyName = name
      this.isModalShown = !this.isModalShown
    },
  },
}
</script>

<style lang="scss" scoped>
@import '~/assets/media_mixin';

.vacancies {
  padding: 8em 0;
  @include _600() {
    padding: 4em 0 1em;
  }
  .vacancies-info {
    &__text {
      max-width: 800px;
      @include _950() {
        max-width: none;
      }
      .article {
        line-height: 1.62em;
        color: #999;
        @include _700() {
          font-size: 0.9em;
        }
      }
      .header {
        margin-bottom: 1em;
      }
    }
    .vacancy {
      &__header {
        width: fit-content;
        transition: color 0.2s ease-out, border-bottom-color 0.2s ease-out;
        cursor: pointer;
        span {
          border-bottom: 1px dotted #000;
          &:after {
            content: '';
            position: absolute;
            height: 0;
            width: 0;
            border: 0 solid transparent;
            margin-top: 0.3em;
            margin-left: 0.2em;
            border-width: 0.3em 0.25em;
            border-top-color: #111;
            transform-origin: 50% 0.15em;
            transition: transform 0.2s ease-out;
          }
        }

        &:hover {
          color: #d81428;
          border-bottom-color: #d81428;
        }
      }
      &__info {
        max-height: 0;
        height: 0;
        overflow: hidden;
        opacity: 0;
        transition: height 0.3s ease-out, opacity 0.3s ease-out;
        li {
          &::marker {
            font-size: 0.8em;
          }
        }
      }
      .show {
        max-height: fit-content;
        height: fit-content;
        opacity: 1;
        transition: height 0.3s ease-out, opacity 0.3s ease-out;
        border-bottom: 1px solid rgb(223, 223, 223);
      }
      .rotateIcon {
        &:after {
          transform: rotate(180deg);
        }
      }
      &__apply {
        margin: 2em 0;
      }
    }
  }
}
</style>
