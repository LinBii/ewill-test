<script setup></script>

<template>
  <section class="background">
    <div class="topic">
      <h1 class="topic first">There is no one</h1>
      <h1 class="topic second">who loves pain</h1>
      <a role="button" href="#form" class="button">FORM</a>
    </div>
    <div class="paragraph-block">
      <div>
        <div class="container">
          <img src="../src/assets/icon/cactus.svg" />
          <h2 class="paragraph">paragraph</h2>
          <img src="../src/assets/icon/cactus.svg" />
        </div>
        <ol class="text">
          <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit</li>
        </ol>
      </div>
      <div>
        <div class="container">
          <img src="../src/assets/icon/cactus.svg" />
          <h2 class="paragraph">paragraph</h2>
          <img src="../src/assets/icon/cactus.svg" />
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
    </div>
  </section>
  <section>
    <div class="wave">Wave</div>
  </section>
  <section class="content">
    <h1 id="form">FORM</h1>
    <form action="">
      <div class="form-list">
        <div>
          <label for="store">store </label>
          <div class="asterisk">*</div>
          <input
            type="text"
            name="store"
            id="store"
            class="form-input"
            placeholder="placeholder text"
            required
          />
        </div>
        <div>
          <label for="name">name </label>
          <div class="asterisk">*</div>
          <input
            type="text"
            name="name"
            id="name"
            class="form-input"
            placeholder="placeholder text"
            required
          />
        </div>
        <div>
          <label for="phone">phone </label>
          <div class="asterisk">*</div>
          <input
            type="number"
            name="phone"
            id="phone"
            class="form-input"
            placeholder="placeholder text"
            required
          />
        </div>
        <div>
          <label for="consumption">Amount of consumption </label>
          <div class="asterisk">*</div>
          <input
            type="number"
            name="consumption"
            id="consumption"
            class="form-input"
            placeholder="placeholder text"
            required
          />
        </div>
        <div>
          <label for="payment">payment </label>
          <div class="asterisk">*</div>
          <select name="payment" id="payment" class="form-input" required>
            <option value="digital payment">digital payment</option>
            <option value="atm">ATM</option>
          </select>
        </div>
      </div>

      <button class="button submit">submit</button>
    </form>
    <div class="cards">
      <div class="card">A</div>
      <div class="card">B</div>
      <div class="card">C</div>
      <div class="card">D</div>
      <div class="card">E</div>
      <div class="card">F</div>
      <div class="card">G</div>
      <div class="card">H</div>
    </div>
    <div class="content motto">
      <h1 class="content motto number">13.32</h1>
      <h1>who seeks after it and</h1>
      <h1>wants to have it</h1>
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
