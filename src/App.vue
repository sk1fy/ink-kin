<script setup>
import { provide, ref, reactive, computed } from 'vue';
const questions = reactive([
  {
    query: "В компании (на вечеринке) Вы:",
    type: 'ei',
    answer: [
      {
        value: true,
        label: 'общаетесь со многими, включая и незнакомцев',
      },
      {
        value: false,
        label: 'общаетесь с немногими - Вашими знакомыми',
      },
    ]
  },
  {
    query: "Вы человек скорее:",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'реалистичный, чем склонный теоретизировать',
      },
      {
        value: false,
        label: 'склонный теоретизировать, чем реалистичный',
      },
    ]
  },
  {
    query: "По-вашему, что хуже:",
    type: 'sn',
    answer: [
      {
        value: true,
        label: '"витать в облаках"',
      },
      {
        value: false,
        label: 'придерживаться проторенной дорожки',
      },
    ]
  },
  {
    query: "Вы более подвержены влиянию:",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'принципов, законов',
      },
      {
        value: false,
        label: 'эмоций, чувств',
      },
    ]
  },
  {
    query: "Вы более склонны",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'убеждать',
      },
      {
        value: false,
        label: 'затрагивать чувства',
      },
    ]
  },
  {
    query: "Вы предпочитаете работать",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'выполняя все точно в срок',
      },
      {
        value: false,
        label: 'не связывая себя определенными сроками',
      },
    ]
  },
  {
    query: "Вы склонны делать выбор",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'довольно осторожно',
      },
      {
        value: false,
        label: 'внезапно, импульсивно',
      },
    ]
  },
  {
    query: "В компании (на вечеринке) Вы",
    type: 'ei',
    answer: [
      {
        value: true,
        label: 'остаетесь допоздна, не чувствуя усталости',
      },
      {
        value: false,
        label: 'быстро утомляетесь и предпочитаете пораньше уйти',
      },
    ]
  },
  {
    query: "Вас более привлекают",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'здравомыслящие люди',
      },
      {
        value: false,
        label: 'люди с богатым воображением',
      },
    ]
  },
  {
    query: "Вам интересно",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'то, что происходит в действительности',
      },
      {
        value: false,
        label: 'те события, которые могут произойти',
      },
    ]
  },
  {
    query: "Оценивая поступки людей, Вы больше учитываете",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'требования закона, чем обстоятельства',
      },
      {
        value: false,
        label: 'обстоятельства, чем требования закона',
      },
    ]
  },
  {
    query: "Обращаясь к другим, Вы склонны",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'соблюдать формальности, этикет',
      },
      {
        value: false,
        label: 'проявлять свои личные, индивидуальные качества',
      },
    ]
  },
  {
    query: "Вы человек скорее",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'точный, пунктуальный',
      },
      {
        value: false,
        label: 'неторопливый, медлительный',
      },
    ]
  },
  {
    query: "Вас больше беспокоит необходимость",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'оставлять дела незаконченными',
      },
      {
        value: false,
        label: 'непременно доводить дела до конца',
      },
    ]
  },
  {
    query: "В кругу знакомых Вы, как правило",
    type: 'ei',
    answer: [
      {
        value: true,
        label: 'в курсе происходящих событий',
      },
      {
        value: false,
        label: 'узнаете о новостях с опозданием',
      },
    ]
  },
  {
    query: "Повседневные дела Вам нравится делать",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'общепринятым способом',
      },
      {
        value: false,
        label: 'своим оригинальным способом',
      },
    ]
  },
  {
    query: "Предпочитаю таких писателей, которые",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'выражаются буквально, напрямую',
      },
      {
        value: false,
        label: 'пользуются аналогиями, иносказаниями',
      },
    ]
  },
  {
    query: "Что Вас больше привлекает",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'стройность мысли',
      },
      {
        value: false,
        label: 'гармония человеческих отношений',
      },
    ]
  },
  {
    query: "Вы чувствуете себя увереннее",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'в логических умозаключениях',
      },
      {
        value: false,
        label: 'в практических оценках ситуаций',
      },
    ]
  },
  {
    query: "Вы предпочитаете, когда дела",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'решены и устроены',
      },
      {
        value: false,
        label: 'не решены и пока не улажены',
      },
    ]
  },
  {
    query: "Как по-вашему, Вы человек, скорее",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'серьезный, определенный',
      },
      {
        value: false,
        label: 'беззаботный, беспечный',
      },
    ]
  },
  {
    query: "При телефонных разговорах Вы",
    type: 'ei',
    answer: [
      {
        value: true,
        label: 'заранее не продумываете все, что нужно сказать',
      },
      {
        value: false,
        label: 'мысленно "репетируете" то, что будет сказано',
      },
    ]
  },
  {
    query: "Как Вы считаете, факты",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'важны сами по себе',
      },
      {
        value: false,
        label: 'есть проявления общих закономерностей',
      },
    ]
  },
  {
    query: "Фантазеры, мечтатели обычно",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'раздражают Вас',
      },
      {
        value: false,
        label: 'довольно симпатичны Вам',
      },
    ]
  },
  {
    query: "Вы чаще действуете как человек",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'хладнокровный',
      },
      {
        value: false,
        label: 'вспыльчивый, горячий',
      },
    ]
  },
  {
    query: "Как по-вашему, хуже быть",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'несправедливым',
      },
      {
        value: false,
        label: 'беспощадным',
      },
    ]
  },
  {
    query: "Обычно Вы предпочитаете действовать",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'тщательно взвесив все возможности',
      },
      {
        value: false,
        label: 'полагаясь на волю случая',
      },
    ]
  },
  {
    query: "Вам приятнее",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'покупать что-нибудь',
      },
      {
        value: false,
        label: 'иметь возможность купить',
      },
    ]
  },
  {
    query: "В компании Вы, как правило",
    type: 'ei',
    answer: [
      {
        value: true,
        label: 'первым заводите беседу',
      },
      {
        value: false,
        label: 'ждете, когда с Вами заговорят',
      },
    ]
  },
  {
    query: "Здравый смысл",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'редко ошибается',
      },
      {
        value: false,
        label: 'часто попадает впросак',
      },
    ]
  },
  {
    query: "Детям часто не хватает",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'практичности',
      },
      {
        value: false,
        label: 'воображения',
      },
    ]
  },
  {
    query: "В принятии решений Вы руководствуетесь скорее",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'принятыми нормами',
      },
      {
        value: false,
        label: 'своими чувствами, ощущениями',
      },
    ]
  },
  {
    query: "Вы человек скорее",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'твердый, чем мягкий',
      },
      {
        value: false,
        label: 'мягкий, чем твердый',
      },
    ]
  },
  {
    query: "Что, по-вашему, больше впечатляет",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'умение методично организовать',
      },
      {
        value: false,
        label: 'умение приспособиться и довольствоваться достигнутым',
      },
    ]
  },
  {
    query: "Вы больше цените",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'определенность, законченность',
      },
      {
        value: false,
        label: 'открытость, многовариантность',
      },
    ]
  },
  {
    query: "Новые и нестандартные отношения с людьми",
    type: 'ei',
    answer: [
      {
        value: true,
        label: 'стимулируют, придают Вам энергии',
      },
      {
        value: false,
        label: 'утомляют Вас',
      },
    ]
  },
  {
    query: "Вы чаще действуете как",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'человек практического склада',
      },
      {
        value: false,
        label: 'человек оригинальный, необычный',
      },
    ]
  },
  {
    query: "Вы более склонны",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'находить пользу в отношениях с людьми',
      },
      {
        value: false,
        label: 'понимать мысли и чувства других',
      },
    ]
  },
  {
    query: "Что приносит Вам больше удовлетворения",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'тщательное и всесторонне обсуждение спорного вопроса',
      },
      {
        value: false,
        label: 'достижение соглашения по поводу спорного вопроса',
      },
    ]
  },
  {
    query: "Вы руководствуетесь более",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'рассудком',
      },
      {
        value: false,
        label: 'велениями сердца',
      },
    ]
  },
  {
    query: "Вам удобнее выполнять работу",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'по предварительной договоренности',
      },
      {
        value: false,
        label: 'которая подвернулась случайно',
      },
    ]
  },
  {
    query: "Вы обычно полагаетесь",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'на организованность, порядок',
      },
      {
        value: false,
        label: 'на случайность, неожиданность',
      },
    ]
  },
  {
    query: "Вы предпочитаете иметь",
    type: 'ei',
    answer: [
      {
        value: true,
        label: 'много друзей на непродолжительный срок',
      },
      {
        value: false,
        label: 'несколько старых друзей',
      },
    ]
  },
  {
    query: "Вы руководствуетесь в большей степени",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'фактами, обстоятельствами',
      },
      {
        value: false,
        label: 'общими положениями, принципами',
      },
    ]
  },
  {
    query: "Вас больше интересуют",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'производство и сбыт продукции',
      },
      {
        value: false,
        label: 'проектирование и исследования',
      },
    ]
  },
  {
    query: "Что Вы считаете за комплимент",
    type: 'tf',
    answer: [
      {
        value: true,
        label: '"Вот очень логичный человек"',
      },
      {
        value: false,
        label: '"Вот тонко чувствующий человек"',
      },
    ]
  },
  {
    query: "Вы более цените в себе",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'невозмутимость',
      },
      {
        value: false,
        label: 'увлеченность',
      },
    ]
  },
  {
    query: "Вы предпочитаете высказывать",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'окончательные и определенные утверждения',
      },
      {
        value: false,
        label: 'предварительные и неоднозначные утверждения',
      },
    ]
  },
  {
    query: "Вы лучше чувствуете себя",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'после принятия решения',
      },
      {
        value: false,
        label: 'не ограничивая себя решениями',
      },
    ]
  },
  {
    query: "Общаясь с незнакомыми, Вы",
    type: 'ei',
    answer: [
      {
        value: true,
        label: 'легко завязываете продолжительные беседы',
      },
      {
        value: false,
        label: 'не всегда находите общие темы для разговора',
      },
    ]
  },
  {
    query: "Вы больше доверяете",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'своему опыту',
      },
      {
        value: false,
        label: 'своим предчувствиям',
      },
    ]
  },
  {
    query: "Вы чувствуете себя человеком",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'более практичным, чем изобретательным',
      },
      {
        value: false,
        label: 'более изобретательным, чем практичным',
      },
    ]
  },
  {
    query: "Кто заслуживает большего одобрения",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'рассудительный, здравомыслящий человек',
      },
      {
        value: false,
        label: 'человек, глубоко переживающий',
      },
    ]
  },
  {
    query: "Вы более склонны",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'быть прямым и беспристрастным',
      },
      {
        value: false,
        label: 'сочувствовать людям',
      },
    ]
  },
  {
    query: "Что, по-вашему, предпочтительней",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'удостовериться, что все подготовлено и улажено',
      },
      {
        value: false,
        label: 'предоставить событиям идти своим чередом',
      },
    ]
  },
  {
    query: "Отношения между людьми должны строиться",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'на предварительной взаимной договоренности',
      },
      {
        value: false,
        label: 'в зависимости от обстоятельств',
      },
    ]
  },
  {
    query: "Когда звонит телефон, Вы",
    type: 'ei',
    answer: [
      {
        value: true,
        label: 'торопитесь подойти первым',
      },
      {
        value: false,
        label: 'надеетесь, что подойдет кто-нибудь другой',
      },
    ]
  },
  {
    query: "Что Вы цените в себе больше",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'развитое чувство реальности',
      },
      {
        value: false,
        label: 'пылкое воображение',
      },
    ]
  },
  {
    query: "Вы больше придаете значение",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'тому, что сказано',
      },
      {
        value: false,
        label: 'тому, как сказано',
      },
    ]
  },
  {
    query: "Вы в основном считаете себя",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'трезвым и практичным',
      },
      {
        value: false,
        label: 'сердечным и отзывчивым',
      },
    ]
  },
  {
    query: "Что выглядит большим заблуждением",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'излишняя пылкость, горячность',
      },
      {
        value: false,
        label: 'чрезмерная объективность, беспристрастность',
      },
    ]
  },
  {
    query: "Какие ситуации привлекают Вас больше",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'регламентированные и упорядоченные',
      },
      {
        value: false,
        label: 'неупорядоченные и нерегламентированные',
      },
    ]
  },
  {
    query: "Вы человек, скорее",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'педантичный, чем капризный',
      },
      {
        value: false,
        label: 'капризный, чем педантичный',
      },
    ]
  },
  {
    query: "Вы чаще склонны",
    type: 'ei',
    answer: [
      {
        value: true,
        label: 'быть открытым, доступным людям',
      },
      {
        value: false,
        label: 'быть сдержанным, скрытным',
      },
    ]
  },
  {
    query: "В литературных произведениях Вы предпочитаете",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'буквальность, конкретность',
      },
      {
        value: false,
        label: 'образность, переносный смысл',
      },
    ]
  },
  {
    query: "Что для Вас труднее",
    type: 'sn',
    answer: [
      {
        value: true,
        label: 'находить общий язык с другими',
      },
      {
        value: false,
        label: 'использовать других в своих интересах',
      },
    ]
  },
  {
    query: "Чего бы вы себе больше пожелали",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'ясности размышлений',
      },
      {
        value: false,
        label: 'умения сочувствовать',
      },
    ]
  },
  {
    query: "Что хуже",
    type: 'tf',
    answer: [
      {
        value: true,
        label: 'быть неприхотливым',
      },
      {
        value: false,
        label: 'быть излишне привередливым',
      },
    ]
  },
  {
    query: "Вы предпочитаете",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'запланированные события',
      },
      {
        value: false,
        label: 'незапланированные события',
      },
    ]
  },
  {
    query: "Вы склонны поступать скорее",
    type: 'jp',
    answer: [
      {
        value: true,
        label: 'обдуманно, чем импульсивно',
      },
      {
        value: false,
        label: 'импульсивно, чем обдуманно',
      },
    ]
  }
])

const user_ei = ref(0)  //это бал EI

function updateEi(x) {
  if(x) {
    user_ei.value++
  } else {
    if (user_ei.value) user_ei.value--
  }
}

const user_sn = ref(0); //это бал SN

function updateSn(x) {
  if(x) {
    user_sn.value++
  } else {
    if (user_sn.value) user_sn.value--
  }
}

const user_tf = ref(0); //это бал TF

function updateTf(x) {
  if(x) {
    user_tf.value++
  } else {
    if (user_tf.value) user_tf.value--
  }
}

const user_jp = ref(0); //это бал JP

function updateJp(x) {
  if(x) {
    user_jp.value++
  } else {
    if (user_jp.value) user_jp.value--
  }
}

provide('user_ei', {
  user_ei,
  updateEi
})
provide('user_sn', {
  user_sn,
  updateSn
})
provide('user_tf', {
  user_tf,
  updateTf
})
provide('user_jp', {
  user_jp,
  updateJp
})

const checkIn = ref(0);

provide('check', checkIn)

const user_i = ref('I') //это буква min для EI экстраверсия-интроверсия (Е-I, от англ. Extravertion-Intmvertion)
const user_n = ref('N') //это буква min для SN сенсорика-интуиция (S-N, от англ. Sensation-Intuition)
const user_f = ref('F') //это буква min для TF логичность-чувствование (T-F, от англ. Thinking-Feeling)
const user_p = ref('P') //это буква min для JP решение-восприятие (J-P, от англ. Judging-Perceiving) (планирование-импульсивность)

const result = computed(() => {
  if (user_ei.value > 5) {user_i.value = 'E'} else{user_i.value = 'I'};
  if (user_sn.value > 10) {user_n.value = 'S'} else{user_n.value = 'N'};
  if (user_tf.value > 10) {user_f.value = 'T'} else{user_f.value = 'F'};
  if (user_jp.value > 10) {user_p.value = 'J'} else{user_p.value = 'P'};

  return `${user_i.value}${user_n.value}${user_f.value}${user_p.value}`
})

const dialogVisible = ref(false)

const handleClose = (done) => {
  ElMessageBox.confirm('Are you sure to close this dialog?')
    .then(() => {
      done()
    })
    .catch(() => {
      // catch error
    })
}
</script>

<template>
  <el-container>
    <el-row justify="center">
      <hello-world msg="Vite"></hello-world>
      <el-col>
        <question-wrap>
          <question-select v-for="(question, index) in questions" :key="index++" :itemQuest="question" :id="index"></question-select>
        </question-wrap>
      </el-col>
    </el-row>
  </el-container>
  <!-- <p>Ei - {{ user_ei }}</p>
  <p>Sn - {{ user_sn }}</p>
  <p>Tf - {{ user_tf }}</p>
  <p>Sn - {{ user_jp }}</p>
  <p>{{ checkIn }}</p>
  <p>{{ result }}</p> -->
  <el-button v-if="checkIn > 69" type="success" @click="dialogVisible = true">Закончить</el-button>
  <h2 v-else>Заполните все поля!</h2>

  <el-dialog v-model="dialogVisible">
    <!-- <h1>{{ result }}</h1> -->
    <text-result :res="result"></text-result>
    <template #footer>
      <span class="dialog-footer">
        <el-button type="danger" @click="dialogVisible = false">Закрыть</el-button>
      </span>
    </template>
  </el-dialog>

</template>

<style scoped>
.dialog-footer button:first-child {
  margin-right: 10px;
}
</style>