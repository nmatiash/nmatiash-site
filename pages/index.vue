<template>
<div class="home">
  <section class="section">
    <h1>Сайт писателя Натальи Матяш</h1>
  </section>
  <section class="section home__bio">
    <div class = "home__imageOfMe">
    </div>
    <div class = "home__biotext">
      <p>
        Наталья Евгеньевна Матяш родилась в г. Архангельске 21 августа 1938 года. Во Владивостоке ее семья оказалась в связи с тем, что отец, будучи военным, с разрешения командования прислал документы, по которым они смогли приехать к месту его службы в 1944 г. По приезде семью ожидало  страшное известие о гибели парохода «Ильмень», где служил отец. Судьба экипажа долгое время была неизвестна. Но у этой истории для неё счастливый конец - отец вернулся.
      </p>
      <p>
        Жила семья Натальи Евгеньевны на Первой Речке. В те годы этот жилой массив сплошь состоял из частных домов, как маленькая деревня. Все друг друга знали, и дети в своем обособленном мире были свободны, безмятежны, счастливы. Но в одно мгновение всё рухнуло. Волею судьбы они оказались на Сахалине, в г. Холмске. Наталья Евгеньевна окончила Южно-Сахалинский пединститут, работала в г. Находке учителем истории и русского языка в школе № 10, а затем - в музыкальном училище. Выйдя на пенсию, переехала во Владивосток, и с тех пор по настоящее время работает в библиотеке им. И.У. Басаргина МБУК «ВЦБС» ведущим библиотекарем. Заслуженный работник культуры, ветеран труда.
      </p>
      <p>
        Более 15 лет ведёт массовые мероприятия для детей начальных и средних классов, работает по программам мастер-класса «Юный родовед», историко-патриотического курса «Моё Отечество», книжной гостиной "Траектория чтения". Успешно организует встречи для читателей почтенного возраста клубного краеведческого объединения «Исток». Участвует в реализации инновационных проектов библиотеки, использует при этом современные технологии. Популяризирует работу библиотеки среди школ Ленинского района г. Владивостока. Активно работает с текстами рассказов И.У. Басаргина. Для создания пьес и их постановки на театральных подмостках, ею подготовлено более 20 пьес по произведениям писателя.
      </p>   
      <p>
        Контактный e-mail:
        <a href="mailto:sokol_gen@mail.ru">sokol_gen@mail.ru</a>  
      </p>   
    </div>
  </section>  
  <section class="section">
    <h1>Книги и рассказы</h1>

    <div class="home__cards">
      <div v-for="card in cards" v-bind:key="card.title" class="home__card">
        <img :src="card.img" class="home__card-image">
        <h3>{{ card.title }}</h3>
        <p v-html="card.desc"></p>
        <a :href="card.asset">Скачать</a>
      </div>
    </div>
  </section>  
  <section class="section">
    <h1>Обо мне пишут</h1>
    <a v-for="about in aboutMe" v-bind:key="about.href" :href="about.href">
      {{ about.title }}
      <br>
    </a>
  </section>  
</div>
</template>

<script>
export default {
  name: 'IndexPage',
  data () {
    return {
      imgSrc: require('@/assets/photo.jpg'),
      cards: [
        {
          title: "Память сердца",
          desc: "В книге собраны воспоминания тех, на чью долю выпали тяготы и ужасы Великой Отечественной. Это особая категория переживших войну: они были детьми, когда на крыши их домов начали падать снаряды и бомбы, когда враг ступил на родную землю. Голод и холод военных лет, слёзы матерей и тоска по ушедшим на фронт отцам — это навсегда осталось в памяти сердца каждого из тех, кого теперь называют «Дети войны».Авторы воспоминаний - участники клубного объединения «Исток» при библиотеке им. И.У. Басаргина (МБУК ВЦБС). Литературная обработка Н.Е. Матяш.",
          asset: "memory.pdf",
          img: require('@/assets/serdce.png')
        },
        {
          title: "Приключения пенсионерки",
          desc: "Героиня повествования – милая, добрая, немного наивная пенсионерка Ксения Львовна. Она переходит из одной истории в другую: смертельно напугала грабителя, познакомилась при исключительных обстоятельствах с Аней-узбечкой, потеряла и нашла внука, воспылала внезапной любовью к коту и так далее, и так далее. За всеми вроде непритязательными приключениями пенсионерки мы видим, безусловно,  хорошего человека, умеющего ценить каждый прожитый день, восторгаться миром и не отчаиваться.<br>Улыбнитесь вместе с моей героиней и порадуйтесь жизни, такой прекрасной и неповторимой!",
          asset: "pens.pdf",
          img: require('@/assets/pens.png')
        },     
        {
          title: 'Сборник "Владивосток для меня"',
          desc: "В конце 2022 года Библиотека им. Басаргина выпустила издание, посвящённое дню города. В нём собраны стихотворения и воспоминания жителей города, участников библиотечного клуба 'Исток'. Оформление и иллюстрации - Лена Левша. Редакция текстов - Н.Е. Матяш.",
          asset: "vdk.pdf",
          img: require('@/assets/vdk.png')
        },    
        {
          title: 'Моя Япония (эссе)',
          desc: "Эссе для литературного конкурса «Японский веер Владивостока» размышляет о культурных связях Японии и русского Дальнего Востока.",
          asset: "japan.pdf",
          img: require('@/assets/japan.png')
        },         
        {
          title: 'Маленькая девочка во Владивостоке (рассказ)',
          desc: "В книге рассказана простая, незатейливая история о том, как девочка Маринка с бабушкой провели вместе три дня во Владивостоке. Им было ве- село, свободно, интересно друг с другом. Невольно задумаешься о том, что может сделать один человек для другого, как много значат в жизни сердеч- ное тепло, любовь, восхищение, как важно понять: никогда не нужно терять способность радоваться простым вещам – солнцу, наступившему новому дню и улыбке человека, живущего рядом.",
          asset: "lgrl.pdf",
          img: require('@/assets/lgrl.png')
        },                        
        {
          title: 'Моя жизнь - моя работа. Биография Людмилы Матяш.',
          desc: "Биография Людмилы Ивановны Матяш, родственницы Натальи Матяш, музыканта, преподавателя и просто хорошего человека.",
          asset: "ludmila.pdf",
          img: require('@/assets/luda.jpg')
        },       
        {
          title: 'Горит Тайга (исценировка)',
          desc: "В 2020 году в Библиотеке им. Басаргина Наталья Евгеньевна поставила исценировку по мотивам одноименного рассказа известного приморского прозаика И.У. Басаргина.",
          asset: "taiga.pdf",
          img: require('@/assets/taiga.png')
        },                                   
        {
          title: 'Крушение жизни (рассказ)',
          desc: "",
          asset: "life.pdf",
          img: null
        },    
        {
          title: 'Я бабушка (рассказ)',
          desc: "",
          asset: "granny.pdf",
          img: null
        },
        {
          title: 'Сын (рассказ)',
          desc: "",
          asset: "son.pdf",
          img: null
        },                            
      ],
      aboutMe: [
        {
          title: "Рассказ 'Вирусная история' на сайте Пенсионер25.рф",
          href: "https://пенсионер25.рф/tvorchestvo/5-virusnaja-istorija.html"
        },
        {
          title: "Моя семья: Рецепт семейного счастья Рахимовых ",
          href: "https://vladlib.ru/n16_11_20_3/"
        },   
        {
          title: "«Мои увлечения»: писательская деятельность Матяш Натальи Евгеньевны, ведущего библиотекаря библиотеки им. И.У. Басаргина",
          href: "https://vladlib.ru/n15_05_20_2/"
        },                     
      ]
    }
  }  
}
</script>

<style lang="scss">
$breakpoint-tablet: 768px;

body {
  background-color: #FDEEDC;
  font-family: Tahoma, sans-serif;  
}

h1 {
  font-size: 2.5em;
}

.home {
  display: flex;
  flex-direction: column;
  padding: 1em;

  &__bio {
    margin: 0;
    display: flex;
    border: 2px solid #333;
    margin-bottom: 2rem;

    @media (max-width: $breakpoint-tablet) {
      display: block;
    }
  }  

  &__biotext {
    margin: 1rem;
    flex: 2;
    text-align: justify;
  }  

  &__imageOfMe {
    background-image: url("@/assets/photo.jpg");
    flex: 1;
    background-size: cover;
    background-position: center;  
    
    @media (max-width: $breakpoint-tablet) {
      height: 70vh;
    }    
  }

  &__cards {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;

    @media (max-width: $breakpoint-tablet) {
      grid-template-columns: 1fr;
    }       
  }

  &__card {
    border: 1px solid #333;   
    padding: 1em; 
  }

  &__card-image {
    width: 100%;
  }
}

</style>
