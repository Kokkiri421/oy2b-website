<template>
  <div class="container">
    <hero-block :is-anchor="true" @onClick="scrollToServices">
      <template v-slot:header> Видеонаблюдение </template>
      <template v-slot:description>
        <div class="description">
          <p class="article">
            Доступ к камерам из любой точки мира. <br />
            Безопасность персонала и Ваших данных.<br />
            Просмотр онлайн через браузер и приложения IOS / Android.<br />
            <span class="dn-600">
              Возможность автоматического контроля за сотрудниками и
              объектами.<br />
              Настройки детекции на конкретное событие или параметр.<br />
              Анализ информации, сбор статистики и формирование отчетов.
            </span>
          </p>
        </div>
      </template>
      <template v-slot:form-prefix>
        Проверьте возможность подключения сервисов и услуг:
      </template>
    </hero-block>
    <div class="wrapper">
      <div class="page-content">
        <service-list class="page-content-block" ref="next-page">
          <service-block :background-color="'#0a78dc'" @onClick="scrollToOrder">
            <template v-slot:header> Видеоаналитика для бизнеса </template>
            <template v-slot:description>
              <div class="paragraph">
                <b>Подсчет вошедших/вышедших посетителей</b>
                <ul>
                  <li>
                    Настройка линии подсчета в произвольном месте изображения
                  </li>
                  <li>
                    Определение часов и дней с максимальной интенсивностью
                    клиентопотока
                  </li>
                  <li>
                    Построение графиков, создание отчетов за выбранный период
                    времени
                  </li>
                </ul>
              </div>
              <div class="paragraph">
                <b>Контроль наличия сотрудников на рабочих местах</b>
                <ul>
                  <li>
                    Настройка линии подсчета в произвольном месте изображения
                  </li>
                  <li>
                    Определение часов и дней с максимальной интенсивностью
                    клиентопотока
                  </li>
                  <li>
                    Построение графиков, создание отчетов за выбранный период
                    времени
                  </li>
                </ul>
              </div>
              <div class="paragraph">
                <b>Тепловые карты маршрутов движения</b>
                <ul>
                  <li>Определение маршрутов движения посетителей</li>
                  <li>
                    Статистика движения и цветовая визуализация движения в кадре
                  </li>
                  <li>Настройка чувствительности детектора активности</li>
                </ul>
              </div>
              <div class="paragraph">
                <b>Определение длины очереди</b>
                <ul>
                  <li>
                    Точная конверсия посетителей в покупателей по дням/часам
                  </li>
                  <li>Отслеживание ситуации в реальном времени</li>
                  <li>Построение графиков и создание отчетов</li>
                </ul>
              </div>
            </template>
            <template v-slot:button
              ><button class="dialog-button">Заказать</button>
            </template>
          </service-block>
          <service-block
            :background-color="'#0a78dc'"
            @onClick="scrollToOrder"
            :is-grey="true"
          >
            <template v-slot:header>Модули распознавания </template>
            <template v-slot:description>
              <div class="paragraph">
                <b>Распознавание наличия униформы</b>
                <ul>
                  <li>
                    Детекция и распознавание наличия/отсутствия спецодежды и
                    касок
                  </li>
                  <li>
                    Настройка оповещений о появлении в кадре сотрудника без
                    спецодежды
                  </li>
                </ul>
              </div>
              <div class="paragraph">
                <b>Распознавание автомобильных номеров</b>
                <ul>
                  <li>Определение автомобильных номеров в кадре</li>
                  <li>
                    Просмотр всех распознанных номеров и поиск по ним в архиве
                  </li>
                  <li>Определение сторонних номеров</li>
                  <li>Интеграция с сервисом «умный шлагбаум»</li>
                </ul>
              </div>
              <div class="paragraph">
                <b>Распознавание лиц</b>
                <ul>
                  <li>
                    Подсчет и сегментация посетителей по полу, возрасту и другим
                    категориям
                  </li>
                  <li>Выделение лиц в видеопотоке и идентификация по базе</li>
                  <li>Отчеты по идентифицированным лицам</li>
                  <li>Определение длины очереди</li>
                </ul>
              </div>
            </template>
            <template v-slot:button
              ><button class="dialog-button">Заказать</button>
            </template>
          </service-block>
          <service-block
            :background-color="'#0a78dc'"
            @onClick="scrollToOrder"
            :is-grey="true"
          >
            <template v-slot:header>Сервисы детекции </template>
            <template v-slot:description>
              <div class="paragraph">
                <b>Детектор движения</b>
                <ul>
                  <li>Определение времени начала и окончания движения</li>
                  <li>Определение координатов объектов</li>
                  <li>Индексация движения с сохранением в архив</li>
                  <li>
                    Оповещения о детекции и настройка чувствительности детектора
                    движения
                  </li>
                </ul>
              </div>
              <div class="paragraph">
                <b>Индикация звука</b>
                <ul>
                  <li>Запись звука видеокамеры</li>
                  <li>Определение превышения звука</li>
                  <li>
                    Настройка уровня допустимой громкости и настройка
                    чувствительности детектора звука
                  </li>
                </ul>
              </div>
              <div class="paragraph">
                <b>Оповещение об оставленных предметах в кадре</b>
                <ul>
                  <li>
                    Определение новых предметов, оставленных в кадре, времени их
                    появления
                  </li>
                  <li>
                    Указание времени, по истечении которого, предмет будет
                    считаться оставленным
                  </li>
                  <li>Настройка габаритов предмета</li>
                </ul>
              </div>
              <div class="paragraph">
                <b>Детектор саботажа камеры</b>
                <ul>
                  <li>
                    Определение расфокусировки, засветки, изменения положения и
                    закрытие объектива камеры
                  </li>
                  <li>Настройка оповещений о саботаже</li>
                  <li>Запись моментов саботажа в архив</li>
                </ul>
              </div>
            </template>
            <template v-slot:button
              ><button class="dialog-button">Заказать</button>
            </template>
          </service-block>
          <service-block :background-color="'#0a78dc'" @onClick="scrollToOrder">
            <template v-slot:header>Интеграция </template>
            <template v-slot:description>
              <p class="article">
                Что делать, если у вас уже закуплены камеры и сервера для
                построения системы видеонаблюдения, либо имеется услуга как
                таковая, но не устраивает качество? А возможно, ваш прошлый или
                приходящий айтишник состряпал всё на коленке, и уже давно не
                работает на вас?
              </p>
              <p class="article">
                Специалисты Oyster Telecom проведут бесплатный аудит и предложат
                наиболее комфортные для вашего бюджета варианты интеграции
                видеоаналитики.
              </p>
              <p class="article">
                Если понадобится, обеспечим доступ к существующему
                видеонаблюдению с помощью услуги «проброс портов».
              </p>
            </template>
            <template v-slot:button
              ><button class="dialog-button">Заказать</button>
            </template>
          </service-block>
        </service-list>
        <special-price class="page-content-block" :background-color="'#0a78dc'"
          ><template v-slot:text
            ><span
              >При необходимости, специалисты компании помогут обеспечить доступ
              к уже существующему видеонаблюдению с помощью услуги
              <strong>«проброс портов»</strong>.
            </span>
          </template></special-price
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
          <p class="article">
            Наши специалисты разработают для вас индивидуальный тарифный план,
            в&nbsp;соответствии с &nbsp;особенностями вашего бизнеса,
            количеством и&nbsp;оснащенностью рабочих мест, степенью нагрузки
            на&nbsp;интернет канал.
          </p>
          <p class="article">
            <br />Конкретное решение зависит от ваших потребностей
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
import SpecialPrice from '~/components/Common/SpecialPrice'
import SlaBlock from '~/components/ItOutsource/SlaBlock'
import CallUsBlock from '~/components/Index/CallUsBlock'
import PriceForm from '~/components/ItOutsource/PriceForm'
export default {
  head() {
    return {
      title: 'Видеонаблюдение для бизнеса в Санкт-Петербурге',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content:
            'Заказать услуги видеонаблюдения для бизнеса в Санкт-Петербурге от компании Oyster Telecom. Быстрая настройка!',
        },
      ],
    }
  },
  components: {
    HeroBlock,
    ServiceBlock,
    ServiceList,
    QuestionBlock,
    SpecialPrice,
    SlaBlock,
    CallUsBlock,
    PriceForm,
  },
  methods: {
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
}
</script>

<style lang="scss" scoped>
@import '~/assets/media_mixin';
.hero-block {
  &__user-form {
    margin-top: 2em;

    .blue-dialog-button {
      background-color: #009ee3;
      &:hover {
        background-color: #17b8ff;
      }
    }
    .dialog-button:nth-child(1) {
      margin-right: 1em;
    }
  }
}
.container {
  display: flex;
  flex-direction: column;
}
.paragraph {
  ul {
    margin-top: 0.5em;
  }
  margin-bottom: 2em;
  &:nth-last-child(-n + 1) {
    margin-bottom: 0;
  }
}
</style>
