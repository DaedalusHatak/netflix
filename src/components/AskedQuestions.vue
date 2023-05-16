<script setup lang="ts">
import { ref } from 'vue'
import GetStartedForm from './GetStartedForm.vue'
const note = "Note that this is not official netflix page!";
interface Question {
  name: string
  answer: string
  isActive: boolean
}
const arrOfQuestions = ref<Question[]>([
  {
    name: 'What is Netflix?',
    answer: `Netflix is a streaming service that offers a wide variety of award-winning TV shows, movies, anime, documentaries, and more on thousands of internet-connected devices.
    
    You can watch as much as you want, whenever you want without a single commercial – all for one low monthly price. There's always something new to discover and new TV shows and movies are added every week!`,
    isActive: false
  },
  {
    name: 'How much does Netflix cost?',
    answer: `Watch Netflix on your smartphone, tablet, Smart TV, laptop, or streaming device, all for one fixed monthly fee. Plans range from 29 zł to 60 zł a month. No extra costs, no contracts.`,
    isActive: false
  },
  {
    name: 'Where can I watch?',
    answer: `Watch anywhere, anytime. Sign in with your Netflix account to watch instantly on the web at netflix.com from your personal computer or on any internet-connected device that offers the Netflix app, including smart TVs, smartphones, tablets, streaming media players and game consoles.

You can also download your favorite shows with the iOS, Android, or Windows 10 app. Use downloads to watch while you're on the go and without an internet connection. Take Netflix with you anywhere.
Note that this is not official netflix page!`,
    isActive: false
  },
  {
    name: 'How do I cancel?',
    answer: `Netflix is flexible. There are no pesky contracts and no commitments. You can easily cancel your account online in two clicks. There are no cancellation fees – start or stop your account anytime.`,
    isActive: false
  },
  {
    name: 'Where can I watch?',
    answer: `Watch anywhere, anytime. Sign in with your Netflix account to watch instantly on the web at netflix.com from your personal computer or on any internet-connected device that offers the Netflix app, including smart TVs, smartphones, tablets, streaming media players and game consoles.

You can also download your favorite shows with the iOS, Android, or Windows 10 app. Use downloads to watch while you're on the go and without an internet connection. Take Netflix with you anywhere.
Note that this is not official netflix page!`,
    isActive: false
  },
  {
    name: 'Where can I watch?',
    answer: `Watch anywhere, anytime. Sign in with your Netflix account to watch instantly on the web at netflix.com from your personal computer or on any internet-connected device that offers the Netflix app, including smart TVs, smartphones, tablets, streaming media players and game consoles.

You can also download your favorite shows with the iOS, Android, or Windows 10 app. Use downloads to watch while you're on the go and without an internet connection. Take Netflix with you anywhere.
`,
    isActive: false
  }
])
</script>

<template>
  <div class="ask-section">
    <h2>Frequently Asked Questions</h2>
    <ul>
      <li v-for="question in arrOfQuestions">
        <h3>
          <button @click="question.isActive = !question.isActive">
            {{ question.name }}
            <p class="add-sign">
              <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
                class="default-ltr-cache-1tgeghn e164gv2o4"
                data-name="Add"
                alt=""
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M11 2V11H2V13H11V22H13V13H22V11H13V2H11Z"
                  fill="currentColor"
                ></path>
              </svg>
            </p>
          </button>
        </h3>
        <div v-if="question.isActive" class="answer">
          <p>
            {{ question.answer }}
            <br><br>
           <b>This is not official netflix page!</b>
          </p>
        </div>
      </li>
    </ul>
    <get-started-form :is-max="'80%'"></get-started-form>
  </div>
</template>

<style scoped lang="scss">
b{
    font-weight: 700;
}
h2{
    text-align: center;
}
h3 {
  margin-bottom: 0.0625rem;
}
svg {
  width: 36px;
  height: 36px;
}
.ask-section {
  padding: 6rem 0;
  ul {
    padding: 0;
    margin: 1.5rem 0 0;
    li {
      list-style: none;
      margin: 0 0 0.5rem 0;
    }
  }
}

button {
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-align: left;
  cursor: pointer;
  color: white;
  background-color: rgba(45, 45, 45, 1);
  border: none;
  font-size: 1.5rem;
  width: 100%;
  max-height: 75rem;
  padding: 1.5rem;
  transition-duration: 250ms;
  transition-property: background-color;
}
button:hover {
  transition-timing-function: cubic-bezier(0.5, 0, 0.1, 1);
  background-color: rgba(78, 78, 78, 1);
}
.add-sign {
  height: 36px;
}
.answer {
  font-size: 1.5rem;
  font-weight: 500;

  white-space: pre-line;
  letter-spacing: normal;
  padding: 1.5rem;
  background-color: rgb(45, 45, 45);
}

</style>
