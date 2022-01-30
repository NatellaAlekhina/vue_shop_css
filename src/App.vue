<template>
  <div>
    <div class="container_main">
      <div class="container">
        <div class="header">
          <div class="header_up">
            <div class="header_up_left">
              <div class="header_up__logo">
                <router-link class="header_logo" to="/"
                  ><h1 class="navi_bar_super">Главная</h1>
                  <img class="header_logo__img" :src="`./img/b_logo.png`" />
                  <p class="bran">BRAN</p>
                  <span class="d">D</span></router-link
                >
              </div>
              <div class="search">
                <form action="#">
                  <details class="browse">
                    <summary>Browse <i class="fas fa-caret-down"></i></summary>
                    <div class="browse_menu">
                      <i class="fa fa-caret-up" aria-hidden="true"></i>
                      <a href="Product.html" class="browse_menu_header">
                        women</a
                      >
                      <hr class="browse_hr" />
                      <a href="Single.html" class="browse_menu_item">Dresses</a>
                      <a href="Single.html" class="browse_menu_item">Tops</a>
                      <a href="Single.html" class="browse_menu_item"
                        >Sweaters/Knits</a
                      >
                      <a href="Single.html" class="browse_menu_item"
                        >Jackets/Coats</a
                      >
                      <a href="Single.html" class="browse_menu_item">Blazers</a>
                      <a href="Single.html" class="browse_menu_item">Denim</a>
                      <a href="Single.html" class="browse_menu_item"
                        >Leggings/Pants</a
                      >
                      <a href="Single.html" class="browse_menu_item"
                        >Skirts/Shorts</a
                      >
                      <a href="Single.html" class="browse_menu_item"
                        >Accessories</a
                      >
                      <a href="Single.html" class="browse_menu_item"
                        >Bags/Purses</a
                      >
                      <a href="Single.html" class="browse_menu_item"
                        >Swimwear/Underwear</a
                      >
                      <a href="Single.html" class="browse_menu_item"
                        >Nightwear</a
                      >
                      <a href="Single.html" class="browse_menu_item"
                        >Shoes Beauty</a
                      >
                      <a href="Product.html" class="browse_menu_header"> men</a>
                      <hr class="browse_hr" />
                      <a href="Single.html" class="browse_menu_item"
                        >Tees/Tank tops</a
                      >
                      <a href="Single.html" class="browse_menu_item"
                        >Shirts/Polos</a
                      >
                      <a href="Single.html" class="browse_menu_item"
                        >Sweaters</a
                      >
                      <a href="Single.html" class="browse_menu_item"
                        >Sweatshirts/Hoodies</a
                      >
                      <a href="Single.html" class="browse_menu_item">Blazers</a>
                      <a href="Single.html" class="browse_menu_item"
                        >Jackets/vests</a
                      >
                    </div>
                  </details>
                  <input
                    class="input"
                    type="text"
                    placeholder="Search for Item..."
                  />
                  <button class="input__lups" type="submit">
                    <i class="fas fa-search"></i>
                  </button>
                </form>
              </div>
            </div>
            <div class="header_up_right">
              <router-link class="nodecor" to="/cart"
                ><h1 class="navi_bar_super">Корзина</h1>
              </router-link>
              <details class="button_cart">
                <summary>My Account <i class="fas fa-caret-down"></i></summary>
                <div class="cart_inside">
                  <a href="Single.html"
                    ><div class="cart_inside_item_1">
                      <div>
                        <img src="img/cart_inside_men.jpg" alt="item" />
                      </div>
                      <div>
                        <p class="unic">Rebox Zane</p>
                        <i class="fa fa-star" aria-hidden="true"></i>
                        <i class="fa fa-star" aria-hidden="true"></i>
                        <i class="fa fa-star" aria-hidden="true"></i>
                        <i class="fa fa-star" aria-hidden="true"></i>
                        <i class="fa fa-star-half-o" aria-hidden="true"></i>
                        <p class="unic_price">1 x $250</p>
                      </div>
                      <div>
                        <i class="fa fa-times-circle" aria-hidden="true"></i>
                      </div></div
                  ></a>
                  <br />
                  <a href="Single.html"
                    ><div class="cart_inside_item_1">
                      <div>
                        <img src="img/cart_inside_girl.jpg" alt="item" />
                      </div>
                      <div>
                        <p class="unic">Rebox Zane</p>
                        <i class="fa fa-star" aria-hidden="true"></i>
                        <i class="fa fa-star" aria-hidden="true"></i>
                        <i class="fa fa-star" aria-hidden="true"></i>
                        <i class="fa fa-star" aria-hidden="true"></i>
                        <i class="fa fa-star-half-o" aria-hidden="true"></i>
                        <p class="unic_price">1 x $250</p>
                      </div>
                      <div>
                        <i class="fa fa-times-circle" aria-hidden="true"></i>
                      </div></div
                  ></a>
                  <br />

                  <p class="cart_total">TOTAL $500.00</p>
                  <button class="cart_button_check">
                    <a href="Checkout.html" class="cart_button_check_text"
                      >Checkout</a
                    >
                  </button>
                  <button class="cart_button_add_to">
                    <a href="ShoppingCart.html" class="cart_button_add_to_text">
                      Go to cart</a
                    >
                  </button>
                </div>
              </details>
            </div>
          </div>
          <hr class="header_up_hr" />
        </div>
      </div>
    </div>
  </div>
  <router-view />
</template>

<script>
const API_URL = "/api/v1";

export default {
  computed: {
    query: {
      get() {
        return this.$store.getters.setQuery;
      },

      set(value) {
        this.$store.commit("setQuery", value);
      },
    },
  },
  mounted() {
    this.$store.dispatch("loadShowcase");
    this.$store.dispatch("loadCart");
  },
};
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
}

header {
  height: 80px;
  padding: 10px 20px;
  background: #ccc;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 50px;

  nav {
    display: flex;
    justify-content: space-between;
    width: 50%;
    align-items: center;
  }
}

/************************* */

* {
  margin: 0;
  padding: 0;
  font-family: "Lato", sans-serif;
}

.container_main {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  //min-height: 100vh;
}

.container {
  margin: 0 auto;
  -webkit-box-flex: 1;
  -ms-flex-positive: 1;
  flex-grow: 1;
}

.header {
  margin-top: 30px;
  margin-bottom: 10px;
}

.header_up {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  width: 1140px;
  margin-left: 50px;
}

.header_up_left {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}

.header_up__logo {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}

.header_logo {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  text-decoration: none;
  height: 48px;
}

.navi_bar_super {
  color: red;
  text-decoration: none;
  font-size: 34px;
  align-self: center;
}

.header_logo__img {
  margin-right: 9px;
}

.bran {
  -webkit-box-align: end;
  -ms-flex-align: end;
  align-items: flex-end;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  margin-bottom: 0;
  text-transform: uppercase;
  color: #222;
  font-size: 27px;
  font-weight: 300;
}

.d {
  -webkit-box-align: end;
  -ms-flex-align: end;
  align-items: flex-end;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  color: #f16d7f;
  font-size: 27px;
  font-weight: 900;
  text-transform: uppercase;
}

.search {
  margin: 10px 0px 0px 30px;
}

form {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  border: 1px solid #e6e6e6;
  border-radius: 3px 3px 3px 3px;
}

.browse {
  width: 87px;
  background-color: #cdcdcc;
  background-image: -webkit-gradient(
    linear,
    left top,
    left bottom,
    from(#f9f9f9),
    to(#f5f5f5)
  );
  background-image: linear-gradient(180deg, #f9f9f9 0%, #f5f5f5 100%);
  border-radius: 3px 0px 0px 3px;
  font-size: 14px;
  line-height: 32px;
  font-weight: 300;
  letter-spacing: 0.025em;
  color: #222222;
  border-right: 1px solid #e6e6e6;
}

summary:hover {
  font-weight: 500;
}

details summary::-webkit-details-marker {
  display: none;
  margin-left: 10px;
}

details > summary {
  list-style: none;
  margin-left: 10px;
}

.browse_menu {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  width: 262px;
  background-color: #ffffff;
  border-radius: 5px;
  -ms-flex-pack: distribute;
  justify-content: space-around;
  position: absolute;
  z-index: 2;
  margin-top: 1px;
}

.fa-caret-up {
  margin: -10px 61px;
  color: white;
}

.browse_menu_header,
.browse_menu_item {
  font-size: 14px;
  line-height: 32px;
  font-weight: 400;
  text-transform: uppercase;
  letter-spacing: 0.025em;
  color: #232323;
  display: block;
  -ms-flex-item-align: center;
  -ms-grid-row-align: center;
  align-self: center;
  width: 100%;
  text-align: left;
  margin-left: 10px;
  text-decoration: none;
}

.browse_menu_item {
  line-height: 28px;
  color: #4f4f4f;
  text-transform: none;
}

.browse_menu_header:hover {
  color: #f16d7f;
}

.browse_menu_item:hover {
  color: #f16d7f;
}

.browse_hr {
  opacity: 0.25;
  color: #e8e8e8;
  width: 236px;
  height: 1px;
  margin: 0;
  margin-left: 10px;
}

.input {
  width: 279px;
  padding-left: 16px;
  color: #a4a4a4;
  font-size: 14px;
  letter-spacing: 0.35px;
  border: none;
}

.input:focus {
  outline: none;
}

.input__lups {
  width: 38px;
  border: none;
  font-size: 14px;
  color: #a4a4a4;
  background-color: #ffffff;
  border-left: 1px solid #e6e6e6;
  border-radius: 0px 3px 3px 0px;
}

.input__lups:hover {
  background-color: #f16d7f;
}

.header_up_right {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}

.button_cart {
  width: 130px;
  height: 38px;
  background-color: #f16d7f;
  color: #ffffff;
  font-size: 15px;
  text-align: center;
  letter-spacing: 0.38px;
  line-height: normal;
  padding-top: 10px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  text-decoration: none;
  margin-left: 26px;
}

.button_cart:hover {
  background-color: #ffffff;
  color: #f16d7f;
  border: 1px solid #f16d7f;
}

.cart_inside {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  width: 262px;
  height: 440px;
  background-color: #ffffff;
  border-radius: 5px;
  position: -webkit-sticky;
  position: sticky;
  z-index: 2;
  margin-top: 15px;
  margin-left: -70px;
}

.cart_inside_item_1 {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  padding-left: 10px;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  padding-right: 15px;
  padding-top: 20px;
}

.cart_inside p {
  margin-bottom: 0;
}

.fa-star,
.fa-star-half-o {
  font-family: "Font Awesome 5 Free";
  font-size: 12px;
  line-height: 1.2;
  font-weight: 900;
  text-transform: uppercase;
  color: #e4af48;
  margin-bottom: 5px;
  margin-right: -5px;
}

.unic {
  font-size: 12px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #222222;
  padding-top: 20px;
  margin-bottom: 5px;
}

.unic_price {
  font-size: 12px;
  line-height: 1.2;
  font-weight: 400;
  text-transform: uppercase;
  color: #f16d7f;
}

.fa-times-circle {
  font-family: FontAwesome;
  font-size: 16px;
  line-height: 1.2;
  font-weight: 400;
  text-transform: uppercase;
  color: #c0c0c0;
  padding-top: 30px;
}

.fa-times-circle:hover {
  color: #f16d7f;
}

.cart_inside_item_1:hover {
  -webkit-filter: brightness(80%);
  filter: brightness(80%);
}

.cart_total {
  font-size: 16px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #222222;
}

.cart_button_check {
  width: 225px;
  height: 50px;
  border: 1px solid #f16d7f;
  margin-left: 10px;
  margin-right: 15px;
  margin-top: 20px;
  background-color: white;
}

.cart_button_check_text {
  font-size: 14px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #f16d7f;
  display: block;
  height: 50px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  margin-top: 15px;
}

.cart_button_check:hover {
  background-color: #f16d7f;
}

.cart_button_check:hover .cart_button_check_text {
  color: white;
}

.cart_button_add_to {
  width: 225px;
  height: 50px;
  background-color: #ffffff;
  border: 1px solid #eaeaea;
  margin-left: 10px;
  margin-right: 15px;
  margin-top: 20px;
}

.cart_button_add_to_text {
  font-size: 14px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #4a4a4a;
  display: block;
  height: 50px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  margin-top: 15px;
}

.cart_button_add_to:hover {
  background: #4a4a4a;
  color: #ffffff;
}

.cart_button_add_to:hover .cart_button_add_to_text {
  color: #ffffff;
}

.header_up_hr {
  color: #ececec;
  height: 1px;
  opacity: 1;
  width: 150vw;
  margin-top: 30px;
  margin-left: -50vw;
}

.menu {
  list-style-type: none;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-pack: distribute;
  justify-content: space-around;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  margin: 0 auto;
  max-width: 680px;
}

.a__menu {
  font-size: 14px;
  line-height: 26px;
  font-weight: 700;
  text-transform: uppercase;
  color: #222222;
  position: relative;
}

.mega_menu {
  display: none;
  max-width: 846px;
  height: 310px;
  background-color: #ffffff;
  border-radius: 5px;
  border: 1px solid #e8e8e8;
  z-index: 2;
  margin-top: 1px;
  position: absolute;
}

.mega_menu:before {
  content: "";
  display: block;
  position: absolute;
  width: 8px;
  height: 8px;
  background-color: #fff;
  -webkit-transform: rotate(45deg);
  transform: rotate(45deg);
  top: -5px;
  left: 20px;
  border-top: #e8e8e8 1px solid;
  border-left: #e8e8e8 1px solid;
}

.a__menu:hover {
  color: #f16d7f;
}

.menu_li:hover .mega_menu {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  visibility: visible;
}

.menu_li__last:hover .mega_menu:before {
  left: 370px;
}

.menu_li__last:hover .mega_menu {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  right: 100px;
}

.menu_li__laster:hover .mega_menu:before {
  left: 430px;
}

.menu_li__laster:hover .mega_menu {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  right: 50px;
}

.ssale-link:hover img {
  -webkit-box-shadow: #f16d7f 0 0 30px;
  box-shadow: #f16d7f 0 0 30px;
  -webkit-transition: 0.5s;
  transition: 0.5s;
}

@-webkit-keyframes saleAnim {
  0% {
    color: white;
  }
  100% {
    color: #f16d7f;
    -webkit-transform: scale(1.25);
    transform: scale(1.25);
  }
}

@keyframes saleAnim {
  0% {
    color: white;
  }
  100% {
    color: #f16d7f;
    -webkit-transform: scale(1.25);
    transform: scale(1.25);
  }
}

.menu-box-unittxt p {
  -webkit-animation: saleAnim 0.5s linear 0s infinite normal;
  animation: saleAnim 0.5s linear 0s infinite normal;
}

.super_text {
  margin-bottom: 0px;
}

.menu-box-unittxt {
  position: absolute;
  right: 15px;
  bottom: 10px;
  color: #ffffff;
  font-size: 22px;
  font-weight: 400;
  line-height: 28px;
  text-transform: uppercase;
  letter-spacing: 0.55px;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
}

.menu-box-list-unit-img {
  position: relative;
}

.browse_mega_menu {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  width: 262px;
  background-color: #ffffff;
  border-radius: 5px;
  -ms-flex-pack: distribute;
  justify-content: space-around;
  z-index: 2;
  margin-top: 1px;
}

.ul_megamenu {
  list-style-type: none;
  padding-left: 0px;
}

/*.footer_main
    width: 1140px */
.container-footerwrap {
  width: 1140px;
  height: 458px;
  margin: 0 auto;
}

.container-footer {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  margin: 0 auto;
  height: 100%;
}

.container-footer h3 {
  color: #f16d7f;
  font-size: 18px;
  font-weight: 700;
  line-height: 85px;
  text-transform: uppercase;
}

.container-footer ul {
  padding-bottom: 25px;
}

.container-footer li,
a {
  list-style: none;
  color: #898989;
  font-size: 16px;
  font-weight: 400;
  line-height: 40px;
  text-decoration: none;
}

.container-footer a:hover {
  color: #f16d7f;
}

.footer-logotext {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  width: 427px;
  margin-top: 18px;
}

.footer-object {
  margin-top: 25px;
}

.footer-object p {
  color: #898989;
  font-size: 14px;
  font-weight: 300;
  line-height: 24px;
  text-align: left;
  text-transform: none;
  padding-top: 13px;
  margin-left: 0;
}

.footer-navwrap {
  margin-top: 23px;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-pack: distribute;
  justify-content: space-around;
  width: 700px;
}

.footer-nawrap-ul {
  padding-left: 0;
}

.a__block {
  display: block;
}

/*.footer_background
    background-color: #e6e6e6
    width: 100vw */
.footer {
  background-color: #e6e6e6;
  width: 100%;
  height: 79px;
}

.footer-copy {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  margin: 0 auto;
  width: 1140px;
  height: 100%;
}

.copy p {
  color: #7a7a7a;
  font-size: 16px;
  font-weight: 400;
  margin-bottom: 0;
}

.footer-soc {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  width: 191px;
}

.footer-soc i {
  color: #ffffff;
  font-size: 32px;
}

.footer-soc a:hover i {
  color: #f16d7f;
}

.slider {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  position: relative;
}

.slider_background {
  background-image: url(img/image_slider.jpg);
  height: 614px;
  width: 1600px;
  margin-left: -200px;
  background-position-x: -50px;
  background-position-y: -50px;
}

.slider_text {
  position: relative;
  position: absolute;
  top: 205px;
  margin-left: 80px;
}

.slider_text::before {
  content: " ";
  position: absolute;
  width: 12px;
  height: 92px;
  background-color: #f16d7f;
  left: -20px;
  top: 16px;
}

.slider_text__h1,
.slider_text__h2,
.slider_text__span {
  font-size: 60px;
  line-height: 1.2;
  font-weight: 900;
  letter-spacing: 0.025em;
  color: #222222;
  margin-bottom: 0;
}

.slider_text__h2,
.slider_text__span {
  font-size: 40px;
}

.slider_text__span {
  font-size: 40px;
  color: #f16d7f;
}

.content__category {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  margin-top: 98px;
}

.content__left_side {
  margin-right: 21px;
}

.img__card {
  position: relative;
  -webkit-box-flex: 1;
  -ms-flex-positive: 1;
  flex-grow: 1;
  padding-bottom: 20px;
}

.img__card:hover {
  -webkit-transform: scale(0.9) translate(2px, 2px);
  transform: scale(0.9) translate(2px, 2px);
}

.img__texting {
  position: absolute;
  height: 82px;
  background-color: #ffffff;
  top: 26px;
  color: #222222;
  font-size: 18px;
  font-weight: bold;
  text-transform: uppercase;
  letter-spacing: 0.45px;
  line-height: normal;
  padding-left: 19px;
  padding-top: 16px;
  padding-right: 20px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  padding-top: 10px;
}

.img__texting1,
.img__texting2 {
  margin-bottom: 0;
}

.img__texting2 {
  color: #f16d7f;
  font-size: 30px;
  font-style: normal;
  letter-spacing: 0.75px;
  line-height: normal;
}

.content__end {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  margin-top: 50px;
}

.content__end_h6 {
  font-size: 30px;
  line-height: 54px;
  font-weight: 700;
  letter-spacing: 0.025em;
  color: #222222;
  margin-bottom: -20px;
}

.end__p {
  font-size: 14px;
  line-height: 54px;
  font-weight: 400;
  letter-spacing: 0.025em;
  color: #9f9f9f;
  text-align: center;
  margin-bottom: 0;
}

.box-product {
  margin-top: 60px;
  margin-bottom: 0;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  width: 1140px;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  margin-left: auto;
  margin-right: auto;
}

.product {
  display: block;
  text-decoration: none;
}

.product-text-box {
  padding: 20px 15px;
}

.product-text {
  color: #222222;
  font-size: 13px;
  font-weight: 400;
  text-transform: uppercase;
  margin-bottom: 0;
  line-height: 1.2;
}

.product-price {
  color: #f16d7f;
  font-size: 16px;
  font-weight: 700;
  text-transform: uppercase;
  margin-bottom: 0;
}

.box-add {
  position: absolute;
  top: 98px;
  display: none;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  width: 100%;
}

.add {
  border: 2px solid #ffffff;
  padding: 8px 12px;
  //color: #ffffff;
  font-size: 13px;
  font-weight: 700;
  text-decoration: none;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}

.add:hover {
  -webkit-box-shadow: 0 0 10px #fff;
  box-shadow: 0 0 10px #fff;
  background-color: #f16d7f;
  opacity: 1.5;
  color: #ffffff;
}

.add-img {
  margin-right: 7px;
}

.item {
  position: relative;
  width: 263px;
  margin-bottom: 40px;
}

.item:hover .box-add {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}

.item:hover {
  -webkit-box-shadow: 0 5px 8px rgba(0, 0, 0, 0.16);
  box-shadow: 0 5px 8px rgba(0, 0, 0, 0.16);
}

.item:hover .product-text {
  font-weight: 600;
  color: #f16d7f;
}

.item:hover .product {
  -webkit-filter: brightness(50%);
  filter: brightness(50%);
}

.button_product {
  width: 212px;
  height: 48px;
  background-color: #f16d7f;
  color: #ffffff;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  text-decoration: none;
  display: block;
  margin-bottom: 113px;
  font-size: 16px;
  line-height: 44px;
  font-weight: 700;
  letter-spacing: 0.025em;
  color: #ffffff;
  padding-left: 25px;
  margin-left: 500px;
}

.button_product:hover {
  color: #f16d7f;
  background-color: #ffffff;
  border: 1px solid #f16d7f;
}

.offer {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  width: 1140px;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 97px;
}

.img__card_offer {
  position: relative;
  -webkit-box-flex: 1;
  -ms-flex-positive: 1;
  flex-grow: 1;
  padding-bottom: 20px;
}

.img__card_offer:hover {
  -webkit-filter: grayscale(80%);
  filter: grayscale(80%);
}

.img__texting_offer {
  position: absolute;
  width: auto;
  text-align: right;
  color: #222222;
  font-size: 18px;
  font-weight: bold;
  font-style: normal;
  letter-spacing: normal;
  line-height: normal;
  text-align: left;
  text-transform: uppercase;
  font-style: normal;
  letter-spacing: 0.45px;
  line-height: normal;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  top: 146px;
  left: 39px;
}

.img__texting_offer_1,
.img__texting_offer_3 {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  text-align: left;
  text-transform: uppercase;
  font-size: 53.7px;
  line-height: 1.2;
  font-weight: 700;
  letter-spacing: 0.025em;
  color: #ffffff;
}

.img__texting_offer_1 p {
  margin-bottom: 0;
}

.img__texting_offer_pink {
  color: #f16d7f;
}

.img__texting_offer_3 {
  font-size: 32.2px;
}

.right_offer {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  background-color: #222224;
  height: 529px;
  padding-top: 48px;
  padding-left: 10px;
}

.img_sup {
  margin-top: 0;
  margin-left: 20px;
  margin-right: 30px;
}

.text_sup {
  height: 104px;
}

.text_sup p {
  margin-bottom: 0;
}

.offer_text_1 {
  font-size: 20px;
  line-height: 1.2;
  font-weight: 700;
  letter-spacing: 0.025em;
  color: #fbfbfb;
}

.offer_text_2 {
  width: 220px;
  font-size: 14px;
  line-height: 24px;
  font-weight: 300;
  letter-spacing: 0.025em;
  color: #fbfbfb;
}

.feedback {
  background-image: -webkit-gradient(
      linear,
      left bottom,
      left top,
      from(#ffffff4d),
      to(#0000004d)
    ),
    url(img/ubscribe_backside.jpg);
  background-image: linear-gradient(to top, #ffffff4d, #0000004d),
    url(img/ubscribe_backside.jpg);
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  height: 438px;
  background-repeat: no-repeat;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  width: 1600px;
  margin-left: -200px;
}

.feedback_list_product {
  margin-left: 0;
}

.feedback_left {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  margin-top: 111px;
  max-width: 570px;
}

.feedback_left_1 {
  margin-left: 25px;
  font-size: 16px;
  line-height: 26px;
  font-weight: 400;
  font-style: italic;
  letter-spacing: 0.025em;
  color: #222224;
  margin-bottom: 0;
}

.feedback_left_2 {
  font-size: 16px;
  line-height: 26px;
  font-weight: 700;
  letter-spacing: 0.025em;
  color: #f16d7f;
  margin-bottom: 0;
  margin-left: 25px;
  margin-top: 19px;
}

.feedback_left_3 {
  font-size: 12px;
  line-height: 14px;
  font-weight: 300;
  color: #222224;
  margin-left: 25px;
  margin-bottom: 0;
}

.pink_horizont,
.pink_horizont_1,
.pink_horizont_2 {
  width: 38px;
  height: 4px;
  background-color: #d6d6d6;
}

.pink_horizont:hover,
.pink_horizont_1:hover,
.pink_horizont_2:hover {
  background-color: #f16d7f;
}

.pink_horizont_boss {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  width: 140px;
  margin-top: 40px;
  margin-left: 25px;
}

.feedback_right {
  max-width: 570px;
  border-left: 1px solid #e0e0e0;
  padding-left: 100px;
  padding-top: 111px;
}

.feedback_right_1 {
  font-size: 24px;
  line-height: 54px;
  font-weight: 400;
  text-transform: uppercase;
  letter-spacing: 0.025em;
  color: #222224;
  text-align: center;
  margin-bottom: -15px;
}

.feedback_right_2 {
  font-size: 14px;
  line-height: 24px;
  text-transform: none;
  text-align: center;
}

.com-rightform input {
  width: 310px;
  height: 45px;
  border-top-left-radius: 23px;
  border-bottom-left-radius: 23px;
  background-color: #e1e1e1;
  border: transparent 1px solid;
  padding-left: 18px;
  color: #222224;
  font-size: 14px;
  font-weight: 400;
  line-height: 54px;
  letter-spacing: 0.35px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  border-right-width: 0;
}

.com-rightform button {
  width: 105px;
  height: 45px;
  border-radius: 0 23px 23px 0;
  background-color: #f16d7f;
  color: #ffffff;
  font-size: 14px;
  font-weight: 400;
  line-height: 35px;
  letter-spacing: 0.35px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  border: #f16d7f 1px solid;
  border-left-width: 0;
  margin-left: -3px;
}

.com-rightform button:hover {
  background-color: white;
  color: #f16d7f;
  border: 1px solid #f16d7f;
}

.com-rightform input:focus,
button:focus {
  outline: none;
}

.com-rightform button:active {
  background-color: white;
  color: #f16d7f;
}

.Checkout_head {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  margin: 0 auto;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  width: 1600px;
  height: 148px;
  background-color: #f8f3f4;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  padding-left: 200px;
  padding-right: 200px;
  margin-left: -200px;
}

.Checkout_head p {
  margin-bottom: 0;
}

.new {
  font-size: 24px;
  line-height: 20px;
  font-weight: 900;
  text-transform: uppercase;
  color: #f16d7f;
}

.dread {
  font-size: 14px;
  line-height: 20px;
  font-weight: 300;
  text-transform: uppercase;
  color: #636363;
}

.dread ol {
  margin-bottom: 0;
}

.breadcrumb-item:hover a {
  color: #f16d7f;
}

.breadcrumb-item + .breadcrumb-item::before {
  float: none;
  padding-left: 0;
  padding-right: 0;
}

.breadcrumb-item.active {
  font-weight: 700;
  color: #f16d7f;
  padding-top: 10px;
  font-size: 14px;
  line-height: 20px;
  text-transform: uppercase;
}

.breadcrumb-item {
  font-size: 14px;
  line-height: 20px;
  font-weight: 300;
  text-transform: uppercase;
  color: #636363;
}

.breadcrumb-item + .breadcrumb-item {
  padding-left: 0;
}

.acor-container {
  width: 1140px;
}

.acor-body {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  max-width: 940px;
}

.acor-container .acor-body {
  height: 0;
  color: rgba(0, 0, 0, 0);
  line-height: 18px;
  padding: 0 30px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  -webkit-transition: color 0.5s, padding 0.5s;
  transition: color 0.5s, padding 0.5s;
  overflow: hidden;
  font-family: Verdana, sans-serif;
  font-size: 16px;
}

.acor-container .acor-body p {
  margin: 0 0 10px;
}

.acor-container input:checked + label + .acor-body {
  height: auto;
  margin-top: -5px;
  color: #000;
  padding: 20px 30px 10px;
  padding-left: 55px;
}

.acor-container input {
  display: none;
}

.acor-container label:before {
  content: "\276F";
  float: right;
}

.acor-container input:checked + label:before {
  -webkit-transition: -webkit-transform 0.35s;
  transition: -webkit-transform 0.35s;
  transition: transform 0.35s;
  transition: transform 0.35s, -webkit-transform 0.35s;
  -webkit-transform: rotate(90deg);
  transform: rotate(90deg);
}

.acor-container input:checked + label {
  font-size: 16px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #222222;
}

.acor-container label {
  display: block;
  padding: 15px 20px;
  width: 100%;
  color: #bfe2ff;
  font-weight: 300;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  z-index: 100;
  font-size: 18px;
  margin: 0 0 5px;
  -webkit-transition: color 0.35s;
  transition: color 0.35s;
  font-size: 16px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #222222;
}

.form_check {
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  border: none;
}

.check_value {
  font-size: 13px;
  line-height: 1.2;
  font-weight: 400;
  text-transform: uppercase;
  color: #222222;
  margin-top: 20px;
}

.check_mini {
  font-size: 13px;
  line-height: 20px;
  font-weight: 400;
  color: #b3b2b2;
}

.input_check_you {
  font-size: 12px;
  line-height: 1.2;
  font-weight: 400;
  text-transform: uppercase;
  color: #222222;
}

.check_easy {
  display: -webkit-inline-box;
  display: -ms-inline-flexbox;
  display: inline-flex;
}

.fa-angle-double-right {
  font-family: FontAwesome;
  font-size: 13px;
  line-height: 20px;
  font-weight: 400;
  color: #b3b2b2;
  padding-top: 2px;
}

.check_button_left {
  width: 180px;
  height: 50px;
  background-color: #ffffff;
  border: 1px solid #eaeaea;
  margin-top: 10px;
}

.check_button_left_text {
  font-size: 14px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #4a4a4a;
  margin-top: 15px;
}

.check_button_left:hover {
  background-color: #f16d7f;
}

.check_button_left:hover .check_button_left_text {
  color: white;
}

.form-check {
  all: none;
}

.forgot {
  font-size: 14px;
  line-height: 20px;
  font-weight: 400;
  color: #222222;
  padding-top: 25px;
  padding-left: 10px;
}

.forgot:hover {
  color: #f16d7f;
}

.password {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}

.input_password {
  font-size: 12px;
  line-height: 20px;
  font-weight: 400;
  color: #222222;
}

.input_password_area {
  display: inline;
  width: 390px;
  height: 45px;
  background-color: #ffffff;
  border: 1px solid #eaeaea;
  margin-bottom: 20px;
  outline: 0;
}

.comment {
  font-size: 13px;
  line-height: 20px;
  font-weight: 400;
  color: #ff0d0d;
}

.comment_red {
  color: #ff0d0d;
}

.slider_single {
  height: 777px;
  background-color: #f7f7f7;
  background-image: url(img/1504_5.jpg);
  background-repeat: no-repeat;
  background-position: center;
  position: relative;
  margin-left: -200px;
  margin-right: auto;
  margin-bottom: 750px;
  width: 1600px;
}

.fa-angle-left,
.fa-angle-right {
  font-size: 24px;
  line-height: 24px;
  top: 375px;
  position: absolute;
  color: #a79b9b;
}

.fa-angle-left {
  left: 15px;
}

.fa-angle-right {
  right: 15px;
  z-index: 2;
}

.slider_single:before {
  content: "";
  position: absolute;
  width: 47px;
  height: 47px;
  background-color: rgba(42, 42, 42, 0.14);
}

.slider_single:before {
  left: 0;
  top: 365px;
}

.slider_single:hover:before {
  background-color: #ef5b70;
}

.slider_single:after {
  content: "";
  position: absolute;
  width: 47px;
  height: 47px;
  background-color: rgba(42, 42, 42, 0.14);
  right: 0;
  top: 365px;
}

.slider_single:hover:after {
  background-color: #ef5b70;
}

.collection_w {
  width: 1140px;
  height: 730px;
  background-color: #ffffff;
  border: 1px solid #eaeaea;
  margin-right: auto;
  position: absolute;
  top: 690px;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-pack: distribute;
  justify-content: space-around;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  margin-left: 280px;
}

.coll_head {
  font-size: 14px;
  line-height: 24px;
  font-weight: 700;
  color: #f16d7f;
  margin-top: 70px;
  margin-bottom: 5px;
}

.coll_head:after {
  content: "";
  width: 63px;
  height: 3px;
  position: absolute;
  background-color: #ef5b70;
  top: 77px;
  left: 529px;
}

.coll_block {
  width: 63px;
  height: 3px;
  background-color: #ef5b70;
}

.coll_mini {
  font-size: 18px;
  line-height: 24px;
  font-weight: 900;
  text-transform: uppercase;
  color: #4d4d4d;
  margin-bottom: 70px;
  margin-top: 10px;
}

.coll_text {
  font-size: 14px;
  line-height: 24px;
  font-weight: 300;
  color: #5e5e5e;
  width: 620px;
  margin-bottom: 24px;
}

.options {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-pack: distribute;
  justify-content: space-around;
  max-width: 370px;
  padding-bottom: 30px;
}

.material {
  font-size: 14px;
  line-height: 24px;
  font-weight: 700;
  color: #b9b9b9;
  margin-right: 37px;
}

.material_s {
  color: #2f2f2f;
  font-size: 14px;
  line-height: 24px;
  font-weight: 700;
}

.price {
  font-size: 24px;
  line-height: 24px;
  font-weight: 700;
  color: #ef5b70;
  margin-bottom: 30px;
}

.choose {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  max-width: 540px;
  margin-top: 30px;
  margin-bottom: 15px;
}

.color {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  margin-right: 70px;
}

.choose_name {
  font-size: 14px;
  line-height: 24px;
  font-weight: 700;
  color: #2f2f2f;
  padding-bottom: 10px;
}

.form-select-sm {
  font-size: 13px;
  line-height: 24px;
  font-weight: 400;
  color: #bcbcbc;
}

.big_add_to_cart {
  width: 537px;
  height: 55px;
  background-color: #ffffff;
  border: 1px solid #ef5b70;
  font-size: 16px;
  line-height: 1.2;
  font-weight: 700;
  color: #ef5b70;
}

.button_end {
  margin-bottom: 120px;
}

.big_add_to_cart:hover {
  background-color: #ef5b70;
  border: 1px solid #ffffff;
  color: #ffffff;
}

.also {
  font-size: 24px;
  line-height: 20px;
  font-weight: 900;
  text-transform: uppercase;
  color: #4d4d4d;
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 240px;
}

.right_offer_horizontal {
  padding-left: 255px;
  background-color: black;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  height: 340px;
  width: 1600px;
  padding-top: 89px;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  padding-right: 255px;
}

.right_offer_horizontal_item .offer_text_2 {
  width: 310px;
}

.right_offer_horizontal_item {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}

.right_offer_horizontal_item .img_sup {
  margin-bottom: 23px;
}

.right_offer_horizontal_item .offer_text_1 {
  margin-bottom: 10px;
  padding-left: 80px;
}

.img_sup_img_sup_big {
  margin-bottom: 18px;
}

.img_sup_img_sup_small {
  margin-bottom: 25px;
}

.container_product_main {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}

.container_product_main .box-product {
  width: 848px;
}

.top_filter_on,
.top_filter_off {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}

.top_filter_on {
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
}

.top_filter_off {
  height: 50px;
  background-color: #f3f3f3;
}

.trend_text_a {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  width: 180px;
}

.trend_text_a ul {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  list-style-type: none;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  padding-left: 0;
}

.trend_text_a ul li {
  display: block;
  height: 25px;
}

.trend_text_a ul li:hover a {
  color: #f16d7f;
}

.add_after:after {
  content: " |";
  color: #dfdfdf;
}

.check_big {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-wrap: wrap;
  flex-wrap: wrap;
  width: 240px;
}

.form-check-label {
  font-family: "Open Sans";
  font-size: 14px;
  line-height: 20px;
  font-weight: 400;
  text-transform: uppercase;
  color: #6f6e6e;
}

.form-check {
  margin-right: 15px;
}

.price_dollar {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}

.trend p {
  margin-bottom: 5px;
}

.price_product p {
  margin-bottom: 0;
}

.form-check-input:checked {
  background-color: #f16d7f;
}

.sort {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  height: 30px;
  background-color: #fff;
  border: 1px solid #ebebeb;
  font-size: 14px;
  line-height: 26px;
  font-weight: 400;
  color: #6f6e6e;
  margin-right: 10px;
  margin-left: 5px;
  margin-top: 10px;
}

.sort_by {
  font-family: Lato;
  font-size: 14px;
  line-height: 26px;
  font-weight: 400;
  color: #6f6e6e;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  min-width: 80px;
  padding-left: 5px;
}

.accordion-button {
  font-size: 14px;
  line-height: 20px;
  font-weight: 700;
  text-transform: uppercase;
  color: #ef5b70;
  width: 243px;
  height: 37px;
}

.accordion-body ul li a {
  font-size: 14px;
  line-height: 33px;
  font-weight: 400;
  color: #6f6e6e;
}

.accordion-body ul li {
  list-style-type: none;
}

.accordion-body ul li:hover a {
  color: #f16d7f;
}

.accordion-button:before {
  content: "";
  width: 5px;
  height: 37px;
  background-color: #ef5b70;
  margin-right: 15px;
}

.accordion-item {
  margin-bottom: 15px;
}

.accordion-button:focus {
  z-index: 3;
  border-color: none;
  -webkit-box-shadow: none;
  box-shadow: none;
}

.accordion-button:not(.collapsed) {
  color: #f16d7f;
  background-color: #ffffff;
  -webkit-box-shadow: none;
  box-shadow: none;
}

.under_g {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
}

.two button {
  width: 150px;
  height: 44px;
  background-color: #ffffff;
  border: 1px solid #ef5b70;
  border-radius: 3px;
  color: #ef5b70;
}

.two:hover button {
  background-color: #ef5b70;
  color: #ffffff;
  border: 1px solid #ffffff;
}

.page-link {
  height: 44px;
  background-color: #ffffff;
  border-radius: 3px;
  font-size: 16px;
  line-height: 26px;
  font-weight: 700;
  color: #c4c4c4;
  border: none;
  padding: 8px;
}

.pagination {
  border: 1px solid #ebebeb;
}

.page-link:hover {
  background-color: #ffffff;
  color: #ef5b70;
}

.products_container {
  margin-bottom: 108px;
  margin-left: 107px;
}

.feature,
.subscribe {
  margin: 0 auto;
}

.product_details {
  max-width: 1140px;
  margin-left: auto;
  margin-right: auto;
  padding: 0px 10px;
}

.menu_product_shop {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  padding-top: 35px;
  padding-bottom: 20px;
}

.menu_product_shop_head1 {
  font-size: 13px;
  line-height: 20px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: -0.015em;
  color: #222222;
  margin-right: 190px;
  width: 200px;
  padding-bottom: 20px;
}

.menu_product_shop_head {
  font-size: 13px;
  line-height: 20px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: -0.015em;
  color: #222222;
  padding-left: 78px;
}

.product_details hr {
  width: 150vw;
  margin-left: -50vw;
  border: 1px solid #ececec;
}

.prod_img:hover {
  -webkit-filter: brightness(80%);
  filter: brightness(80%);
}

.prod_one {
  padding-left: 5px;
}

.prod_opt {
  font-size: 13px;
  line-height: 20px;
  font-weight: 400;
  color: #575757;
}

.prod_cl {
  font-size: 13px;
  line-height: 20px;
  font-weight: 300;
  color: #6f6e6e;
}

.opt_product_all {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: space-between;
  flex-direction: space-between;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}

.menu_product_shop_price3 {
  font-size: 13px;
  line-height: 20px;
  font-weight: 400;
  color: #656565;
  padding-top: 5px;
}

.menu_product_shop_quan {
  font-size: 13px;
  line-height: 20px;
  font-weight: 400;
  color: #656565;
  display: block;
  width: 54px;
  height: 30px;
  background-color: #ffffff;
  border: 1px solid #eaeaea;
  padding-left: 24px;
  padding-top: 5px;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  margin-left: 120px;
  margin-right: 85px;
}

.menu_product_shop_price {
  font-size: 13px;
  line-height: 20px;
  font-weight: 400;
  color: #656565;
  padding-top: 5px;
  margin-right: 120px;
}

.end_shopping {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  margin-top: 25px;
  margin-bottom: 40px;
}

.end_shop {
  width: 235px;
  height: 50px;
  background-color: #ffffff;
  border: 1px solid #eaeaea;
}

.end_shop:hover {
  background-color: #f16d7f;
}

.end_button {
  font-size: 14px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #4a4a4a;
}

.end_button:hover {
  text-decoration: none;
  color: #ffffff;
}

.adress_finish {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  margin-top: 60px;
  margin-bottom: 80px;
}

.wow_form {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  border: none;
}

.form_name_all {
  font-size: 16px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #222222;
  padding-bottom: 10px;
}

.form-select_wow {
  width: 355px;
  height: 45px;
  background-color: #ffffff;
  border: 1px solid #eaeaea;
  font-size: 13px;
  line-height: 1.2;
  font-weight: 300;
  color: #b1b1b1;
  margin-bottom: 10px;
}

.form-select_wow {
  width: 355px;
  height: 45px;
  background-color: #ffffff;
  border: 1px solid #eaeaea;
  font-size: 13px;
  line-height: 1.2;
  font-weight: 300;
  color: #b1b1b1;
  margin-bottom: 10px;
}

.form-select_wow:hover {
  outline: none;
}

.form-select_wow:focus {
  outline: none;
}

.but_on_proc_true {
  width: 100px;
  height: 35px;
  background-color: #ffffff;
  border: 1px solid #eaeaea;
}

.but_on_proc_true:hover {
  background-color: #f16d7f;
}

.wow_new {
  font-size: 11px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #4a4a4a;
  padding-top: 2px;
  padding-left: 2px;
}

.wow_new:hover {
  color: #f3f3f3;
}

.mini_form_name_all {
  padding-bottom: 10px;
  font-size: 14px;
  line-height: 1.2;
  font-weight: 300;
  color: #000000;
}

.proc_to_check {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  width: 360px;
  height: 214px;
  background-color: #f5f3f3;
}

.sub_total {
  font-size: 11px;
  line-height: 1.2;
  font-weight: 400;
  text-transform: uppercase;
  color: #4a4a4a;
  margin: 50px 30px 10px;
  -ms-flex-item-align: end;
  align-self: flex-end;
}

.grand_total {
  font-size: 16px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #222222;
  -ms-flex-item-align: end;
  align-self: flex-end;
  margin: 0px 30px 30px;
}

.grand {
  font-size: 16px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #f16d7f;
}

.but_on_proc_shop {
  width: 273px;
  height: 50px;
  background-color: #f16d7f;
  -ms-flex-item-align: end;
  align-self: flex-end;
  margin: 5px 30px;
  border: none;
}

.but_on_proc_shop:hover {
  background-color: #969191;
  border: 1px #f16d7f;
}

.wow {
  font-size: 16px;
  line-height: 1.2;
  font-weight: 700;
  text-transform: uppercase;
  color: #ffffff;
}

.wow:hover {
  color: #f16d7f;
}

.fa-times-circle {
  padding-bottom: 10px;
  padding-top: 0;
}

.fa-times-circle:hover {
  -webkit-filter: brightness(50%);
  filter: brightness(50%);
}

a {
  text-decoration: none;
}

.nodecor {
  text-decoration: none;
}

/*# sourceMappingURL=style.css.map */
</style>
