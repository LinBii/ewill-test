<script setup></script>

<template>
  <section class="background">
    <div class="topic">
      <h1 class="topic first">There is no one</h1>
      <h1 class="topic second">who loves pain</h1>
      <a role="button" href="#form" class="button">FORM</a>
    </div>
    <div class="paragraph-block">
      <div class="paragraph">
        <div class="container">
          <img src="../src/assets/icon/cactus.svg" />
          <h2>paragraph</h2>
          <img src="../src/assets/icon/cactus.svg" />
        </div>
        <ol class="text">
          <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit</li>
        </ol>
      </div>
      <div class="paragraph">
        <div class="container">
          <img src="../src/assets/icon/cactus.svg" />
          <h2>paragraph</h2>
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
  <section class="waves">
    <img src="../src/assets/icon/waves.svg" />
    <img src="../src/assets/icon/waves.svg" />
  </section>
  <section class="content">
    <div class="form">
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
              type="tel"
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

        <a role="button" href="#" class="button submit">submit</a>
      </form>
    </div>

    <div class="cards">
      <div class="card first-prize">
        A
        <div class="quantity">ONE</div>
        <div class="prize">dehumidifier</div>
      </div>
      <div class="card first-prize">
        B
        <div class="quantity">ONE</div>
        <div class="prize">range hood</div>
      </div>
      <div class="card first-prize">
        C
        <div class="quantity">ONE</div>
        <div class="prize">vacuum cleaner</div>
      </div>
      <div class="card normal-prize">
        D
        <div class="quantity">ONE</div>
        <div class="prize">toaster</div>
      </div>
      <div class="card normal-prize">
        E
        <div class="quantity">ONE</div>
        <div class="prize">scale</div>
      </div>
      <div class="card normal-prize">
        F
        <div class="quantity">ONE</div>
        <div class="prize">straightening iron</div>
      </div>
      <div class="card normal-prize">
        G
        <div class="quantity">FIVE</div>
        <div class="prize">vacuum cleaner</div>
      </div>
      <div class="card normal-prize">
        H
        <div class="quantity">TEN</div>
        <div class="prize">rice cooker</div>
      </div>
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
