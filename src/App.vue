<script setup>
import { ref, watch } from 'vue';

const stores = ['store1', 'store2', 'store3', 'store4', 'store5'];
const filteredStores = ref(stores);

const form = ref('');
const store = ref('');
const name = ref('');
const phone = ref('');
const consumption = ref('');
const payment = ref('digital payment');
const storeError = ref(false);
const nameError = ref(false);
const phoneError = ref(false);
const consumptionError = ref(false);
const paymentError = ref(false);
const submitFailure = ref(false);
const submitSuccess = ref(false);

const storeErrorMessage = ref('');
const nameErrorMessage = ref('');
const phoneErrorMessage = ref('');
const consumptionErrorMessage = ref('');
const paymentErrorMessage = ref('');

const noResult = ref(false);

watch(store, (value) => {
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

const isValidStore = () => filteredStores.value.length === 1;

const isValidName = (nameValue) => {
  const pattern =
    /^[\u0041-\u005A\u0061-\u007A\u4E00-\u9FFF\u3105-\u3129\u02CA\u02C7\u02CB\u02D9]+$/;

  return pattern.test(nameValue);
};

const isValidPhone = (phoneValue) => {
  const pattern = /^09[0-9]{8}$/;
  return pattern.test(phoneValue);
};

const isValidConsumption = (consumptionValue) => {
  const minValue = 0;
  const pattern = /^[0-9]+$/;
  return pattern.test(consumptionValue) && consumptionValue >= minValue;
};

const submitForm = () => {
  if (store.value.trim() === '') {
    submitFailure.value = true;
    storeError.value = true;
    storeErrorMessage.value = 'required';
  } else if (!isValidStore(store.value)) {
    submitFailure.value = true;
    storeError.value = true;
    storeErrorMessage.value = 'wrong format';
  } else {
    storeError.value = false;
    storeErrorMessage.value = '';
  }

  if (name.value.trim() === '') {
    submitFailure.value = true;
    nameError.value = true;
    nameErrorMessage.value = 'required';
  } else if (!isValidName(name.value)) {
    submitFailure.value = true;
    nameError.value = true;
    nameErrorMessage.value = 'wrong format';
  } else {
    nameError.value = false;
    nameErrorMessage.value = '';
  }

  if (phone.value.trim() === '') {
    submitFailure.value = true;
    phoneError.value = true;
    phoneErrorMessage.value = 'required';
  } else if (!isValidPhone(phone.value)) {
    submitFailure.value = true;
    phoneError.value = true;
    phoneErrorMessage.value = 'wrong format';
  } else {
    phoneError.value = false;
    phoneErrorMessage.value = '';
  }

  if (consumption.value === '') {
    submitFailure.value = true;
    consumptionError.value = true;
    consumptionErrorMessage.value = 'required';
  } else if (!isValidConsumption(consumption.value)) {
    submitFailure.value = true;
    consumptionError.value = true;
    consumptionErrorMessage.value = 'wrong format';
  } else {
    consumptionError.value = false;
    consumptionErrorMessage.value = '';
  }

  if (payment.value.trim() === '') {
    submitFailure.value = true;
    paymentError.value = true;
    paymentErrorMessage.value = 'required';
  } else {
    paymentError.value = false;
    paymentErrorMessage.value = '';
  }

  if (
    storeError.value === false &&
    nameError.value === false &&
    phoneError.value === false &&
    consumptionError.value === false &&
    paymentError.value === false
  ) {
    submitFailure.value = false;
    submitSuccess.value = true;
  } else {
    submitFailure.value = true;
    submitSuccess.value = false;
  }
};
</script>

<template>
  <section class="background">
    <div class="topic">
      <h1 class="topic first">There is no one</h1>
      <h1 class="topic second">who loves pain</h1>
      <div class="container">
        <a role="button" href="#form" class="button">FORM</a>
      </div>
    </div>
    <div class="paragraph-block">
      <div class="bubbles">
        <img src="../src/assets/icon/bubble20px.svg" class="big-bubble" />
        <img src="../src/assets/icon/bubble12px.svg" class="small-bubble" />
      </div>
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
              :class="storeError ? 'form-input invalid' : 'form-input'"
              placeholder="placeholder text"
              list="stores"
              v-model="store"
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
            <div v-if="storeError" class="error">
              {{ storeErrorMessage }}
            </div>
          </div>
          <div class="form-control">
            <label for="name">name</label>
            <div class="asterisk">*</div>
            <!-- 允許中文、英文及注音輸入 -->
            <input
              type="text"
              name="name"
              id="name"
              v-model="name"
              :class="nameError ? 'form-input invalid' : 'form-input'"
              placeholder="placeholder text"
              oninput="value=this.value.replace(/[^\u0041-\u005A\u0061-\u007A\u4E00-\u9FFF\u3105-\u3129\u02CA\u02C7\u02CB\u02D9]/g,'')"
              required
            />
            <div v-if="nameError" class="error">
              {{ nameErrorMessage }}
            </div>
          </div>
          <div class="form-control">
            <label for="phone">phone </label>
            <div class="asterisk">*</div>
            <input
              type="tel"
              name="phone"
              id="phone"
              v-model="phone"
              :class="phoneError ? 'form-input invalid' : 'form-input'"
              placeholder="placeholder text"
              pattern="[0]{1}[9]{1}[0-9]{8}"
              oninput="value=this.value.replace(/\D/g,'')"
              maxlength="10"
              required
            />
            <div v-if="phoneError" class="error">
              {{ phoneErrorMessage }}
            </div>
          </div>
          <div class="form-control">
            <label for="consumption">Amount of consumption </label>
            <div class="asterisk">*</div>
            <input
              type="number"
              name="consumption"
              id="consumption"
              v-model="consumption"
              :class="consumptionError ? 'form-input invalid' : 'form-input'"
              placeholder="placeholder text"
              oninput="value=this.value.replace(/\D/g,'')"
              min="0"
              required
            />
            <div v-if="consumptionError" class="error">
              {{ consumptionErrorMessage }}
            </div>
          </div>
          <div class="form-control">
            <label for="payment">payment </label>
            <div class="asterisk">*</div>
            <select
              name="payment"
              id="payment"
              v-model="payment"
              :class="paymentError ? 'form-input invalid' : 'form-input'"
              required
            >
              <option value="digital payment">digital payment</option>
              <option value="atm">ATM</option>
            </select>
            <div v-if="paymentError" class="error">
              {{ paymentErrorMessage }}
            </div>
          </div>
        </div>

        <div class="container">
          <div v-if="submitSuccess">
            <a
              role="button"
              id="success"
              href="#form"
              @click="submitForm"
              class="button submit"
            >
              <img src="../src/assets/icon/success.svg" class="success icon" />
              success</a
            >
          </div>
          <div v-if="submitFailure">
            <a
              role="button"
              id="failure"
              href="#form"
              @click="submitForm"
              class="button submit"
            >
              <img src="../src/assets/icon/failure.svg" class="failure icon" />
              failure</a
            >
          </div>

          <a
            role="button"
            href="#form"
            @click="submitForm"
            class="button submit"
            v-if="!submitSuccess && !submitFailure"
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
