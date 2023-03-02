<script setup>
import { ref, watch } from 'vue';

const stores = ['store1', 'store2', 'store3', 'store4', 'store5'];
const filteredStores = ref(stores);

const form = ref('');
const inputValue = ref('');

const noResult = ref(false);
const missingRequired = ref(false);
const wrongFormat = ref(false);

watch(inputValue, (value) => {
  if (value.length === 0) {
    filteredStores.value = stores;
    noResult.value = false;
    return;
  }

  const inputLower = value.toLowerCase();

  filteredStores.value = stores.filter((option) =>
    option.toLowerCase().includes(inputLower)
  );

  noResult.value = filteredStores.value.length === 0;
});

const submitForm = () => {
  if (form.value.reportValidity()) {
    console.log('Form submitted successfully!');
  }
};
</script>

<template>
  <section class="background">
    <div class="topic">
      <h1 class="topic first">There is no one</h1>
      <h1 class="topic second">who loves pain</h1>
      <a role="button" href="#form" class="button">FORM</a>
    </div>
    <div class="paragraph-block">
      <div class="sup-oar">
        <img src="../src/assets/icon/uppersup.svg" class="uppersup" />
        <img src="../src/assets/icon/oar.svg" class="oar" />
      </div>
      <div class="paragraph">
        <div class="container">
          <img src="../src/assets/icon/cactus.svg" class="cactus" />
          <h2>paragraph</h2>
          <img src="../src/assets/icon/cactus.svg" class="cactus" />
        </div>
        <ol class="text">
          <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit</li>
        </ol>
      </div>
      <div class="paragraph">
        <div class="container">
          <img src="../src/assets/icon/cactus.svg" class="cactus" />
          <h2>paragraph</h2>
          <img src="../src/assets/icon/cactus.svg" class="cactus" />
        </div>
        <ol class="text">
          <li>
            Quisque sodales leo <strong><u>vitae vulputate auctor.</u></strong>
          </li>
          <li>
            Proin ac justo ut nisl tincidunt imperdiet.Maecenas viverra libero a
            pellentesque blandit.
          </li>
          <li>
            Cras tristique tellus id leo bibendum, eu dapibus nisl accumsan.
          </li>
          <li>
            Donec ultrices sapien
            <strong>vitae leo venenatis ullamcorper.</strong>
          </li>
        </ol>
      </div>
      <div class="sup-firework">
        <img src="../src/assets/icon/firework.svg" class="firework" />
        <img src="../src/assets/icon/lowersup.svg" class="lowersup" />
      </div>
    </div>
  </section>
  <section class="waves">
    <img src="../src/assets/icon/waves.svg" />
    <img src="../src/assets/icon/waves.svg" />
  </section>
  <section class="content">
    <div>
      <h1 id="form" class="form">
        FORM<img src="../src/assets/icon/turtle.svg" class="turtle" />
      </h1>
      <form @submit.prevent="submitForm" ref="form">
        <div class="form-list">
          <div class="form-control">
            <label for="store">store</label>
            <div class="asterisk">*</div>
            <div v-if="noResult" class="no-result">no result</div>
            <input
              type="text"
              name="store"
              id="store"
              class="form-input"
              placeholder="placeholder text"
              list="stores"
              v-model="inputValue"
              required
            />
            <datalist id="stores">
              <option
                v-for="store in filteredStores"
                :value="store"
                :key="store"
              >
                {{ store }}
              </option>
            </datalist>
            <div v-if="missingRequired" class="missing-required">required</div>
            <div v-if="wrongFormat" class="missing-required">wrong format</div>
          </div>
          <div class="form-control">
            <label for="name">name</label>
            <div class="asterisk">*</div>
            <!-- 允許中文、英文及注音輸入 -->
            <input
              type="text"
              name="name"
              id="name"
              class="form-input"
              placeholder="placeholder text"
              oninput="value=this.value.replace(/[^\u0041-\u005A\u0061-\u007A\u4E00-\u9FFF\u3105-\u3129\u02CA\u02C7\u02CB\u02D9]/g,'')"
              required
            />
            <div v-if="missingRequired" class="missing-required">required</div>
            <div v-if="wrongFormat" class="missing-required">wrong format</div>
          </div>
          <div class="form-control">
            <label for="phone">phone </label>
            <div class="asterisk">*</div>
            <input
              type="tel"
              name="phone"
              id="phone"
              class="form-input"
              placeholder="placeholder text"
              pattern="[0]{1}[9]{1}[0-9]{8}"
              oninput="value=this.value.replace(/\D/g,'')"
              maxlength="10"
              required
            />
            <div v-if="missingRequired" class="missing-required">required</div>
            <div v-if="wrongFormat" class="missing-required">wrong format</div>
          </div>
          <div class="form-control">
            <label for="consumption">Amount of consumption </label>
            <div class="asterisk">*</div>
            <input
              type="number"
              name="consumption"
              id="consumption"
              class="form-input"
              placeholder="placeholder text"
              oninput="value=this.value.replace(/\D/g,'')"
              min="0"
              required
            />
            <div v-if="missingRequired" class="missing-required">required</div>
            <div v-if="wrongFormat" class="missing-required">wrong format</div>
          </div>
          <div class="form-control">
            <label for="payment">payment </label>
            <div class="asterisk">*</div>
            <select name="payment" id="payment" class="form-input" required>
              <option value="digital payment">digital payment</option>
              <option value="atm">ATM</option>
            </select>
            <div v-if="missingRequired" class="missing-required">required</div>
            <div v-if="wrongFormat" class="missing-required">wrong format</div>
          </div>
        </div>

        <div class="container">
          <a
            role="button"
            href="#"
            @click.prevent="submitForm"
            class="button submit"
            >submit</a
          >
        </div>
      </form>
    </div>

    <div class="sand">
      <div class="cards">
        <div class="card first-prize">
          <div class="prize-name">A</div>
          <img src="../src/assets/icon/certificateA.svg" class="certificateA" />
          <div class="quantity">ONE</div>
          <div class="prize">dehumidifier</div>
        </div>
        <div class="card first-prize">
          <div class="prize-name">B</div>
          <img src="../src/assets/icon/certificateA.svg" class="certificateA" />
          <div class="quantity">ONE</div>
          <div class="prize">range hood</div>
        </div>
        <div class="card first-prize">
          <div class="prize-name">C</div>
          <img src="../src/assets/icon/certificateA.svg" class="certificateA" />
          <div class="quantity">ONE</div>
          <div class="prize">vacuum cleaner</div>
        </div>
        <div class="card normal-prize">
          <div class="prize-name">D</div>
          <img src="../src/assets/icon/certificateD.svg" class="certificateD" />
          <div class="quantity">ONE</div>
          <div class="prize">toaster</div>
        </div>
        <div class="card normal-prize">
          <div class="prize-name">E</div>
          <img src="../src/assets/icon/certificateD.svg" class="certificateD" />
          <div class="quantity">ONE</div>
          <div class="prize">scale</div>
        </div>
        <div class="card normal-prize">
          <div class="prize-name">F</div>
          <img src="../src/assets/icon/certificateD.svg" class="certificateD" />
          <div class="quantity">ONE</div>
          <div class="prize">straightening iron</div>
        </div>
        <div class="card normal-prize">
          <div class="prize-name">G</div>
          <img src="../src/assets/icon/certificateD.svg" class="certificateD" />
          <div class="quantity">FIVE</div>
          <div class="prize">vacuum cleaner</div>
        </div>
        <div class="card normal-prize">
          <div class="prize-name">H</div>
          <img src="../src/assets/icon/certificateD.svg" class="certificateD" />
          <div class="quantity">TEN</div>
          <div class="prize">rice cooker</div>
        </div>
      </div>
    </div>

    <div class="motto">
      <div>
        <div class="vector-left"></div>
        <h1 class="content motto number">13.32</h1>
        <h1 class="motto text">who seeks after it and</h1>
        <h1 class="motto text">wants to have it</h1>
        <div class="vector-right"></div>
      </div>

      <img src="../src/assets/icon/lighthouse.svg" class="lighthouse" />
    </div>
    <div class="shop">
      <div class="topic">
        <h1 class="bottom">
          Neque porro quisquam <br />
          est qui dolorem!
        </h1>
        <img src="../src/assets/icon/market.svg" class="market" />
      </div>
    </div>
  </section>
</template>

<style scoped></style>
