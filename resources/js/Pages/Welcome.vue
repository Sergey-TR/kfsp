<script setup>
import { Head, Link } from "@inertiajs/vue3";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Navigation } from "swiper/modules";
import "swiper/css";
import "swiper/css/navigation";
import MainLayout from "@/Layouts/MainLayout.vue";
import Modal from "@/Components/Modal.vue";
import SecondaryButton from "@/Components/SecondaryButton.vue";
import { ref } from "vue";

const modules = [Navigation];

const swiperImg = ref([
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/Box_TV_02.jpg",
    title: "желейная долька 1",
  },
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/Box_TV_05.jpg",
    title: "желейная долька 2",
  },
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/Box_TV_01.jpg",
    title: "желейная долька 3",
  },
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/Box_TV_03.jpg",
    title: "желейная долька 4",
  },
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/Box_TV_04.jpg",
    title: "желейная долька 5",
  },
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/Box_TV_07.jpg",
    title: "желейная долька 6",
  },
]);

const swiperNew = ref([
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/newchoko150.jpg",
    title: "new product 1",
    description:
      "«Волшебные купола» - любимые конфеты из нежной кремовой основы с декоративной посыпкой из бархатного какао-порошка.",
  },
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/newklub150.jpg",
    title: "new product 2",
    description:
      "«Волшебные купола» - любимые конфеты из нежной кремовой основы с декоративной посыпкой из бархатного какао-порошка.",
  },
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/neworange150.jpg",
    title: "new product 3",
    description:
      "«Волшебные купола» - любимые конфеты из нежной кремовой основы с декоративной посыпкой из бархатного какао-порошка.",
  },
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/newrose108.jpg",
    title: "new product 4",
    description:
      "«Волшебные купола» - любимые конфеты из нежной кремовой основы с декоративной посыпкой из бархатного какао-порошка.",
  },
  {
    img: "https://raw.githubusercontent.com/Sergey-TR/images/main/img/newtrufel150.jpg",
    title: "new product 5",
    description:
      "«Волшебные купола» - любимые конфеты из нежной кремовой основы с декоративной посыпкой из бархатного какао-порошка.",
  },
]);

const openView = ref(false);
const viewItem = ref({});

const quickView = (item) => {
  openView.value = true;
  console.log(item);
  viewItem.value = item;
};

const closeModal = () => {
  openView.value = false;
};
console.log(viewItem.value);
defineProps({
  canLogin: {
    type: Boolean,
  },
  canRegister: {
    type: Boolean,
  },
  laravelVersion: {
    type: String,
    required: true,
  },
  phpVersion: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <MainLayout>
    <Head title="Кондитерская фабрика СП" />
    <div class="wrapper center">
      <div class="w-full h-5"></div>
      <div
        class="relative w-full h-[440px] bg-white border-4 rounded-xl border-main-text"
      >
        <div class="slider absolute top-0 left-0"></div>
      </div>
      <div class="w-full h-8"></div>
      <section class="new">
        <div class="w-full flex flex-col items-center justify-center">
          <h1 class="text-main-text uppercase font-bold h1_hit">новинки</h1>
          <div class="w-full h-8 border-t-2 border-main-text"></div>
          <div
            class="hit_slider_box w-full relative bg-white py-5 flex items-center border-4 rounded-xl border-main-text"
          >
            <Swiper
              :navigation="true"
              :modules="modules"
              :breakpoints="{
                1200: { slidesPerView: 3 },
                768: { slidesPerView: 2 },
                700: { slidersPerView: 1 },
              }"
            >
              <swiper-slide
                v-for="(newItem, idx) in swiperNew"
                :key="idx"
                class="flex flex-col items-center justify-center h-auto relative hit_product"
              >
                <Link
                  href="#"
                  class="flex flex-col items-center justify-center relative w-auto"
                >
                  <div class="w-full">
                    <img
                      :src="newItem.img"
                      height="220"
                      class="w-full object-contain img_new"
                    />
                  </div>
                </Link>

                <div
                  class="popup absolute bottom-9 z-50 hover:cursor-pointer"
                  @click="quickView(newItem)"
                >
                  быстрый просмотр
                </div>
                <Link
                  href="#"
                  class="mt-12 text-lg uppercase text-main-text font-bold absolute bottom-0"
                  >{{ newItem.title }}
                </Link>
                <Modal
                  :maxWidth="`modalProduct`"
                  :show="openView"
                  :img="newItem.img"
                  @close="closeModal"
                >
                  <div
                    class="w-full h-full bg-white p-4 flex flex-col items-center justify-between"
                  >
                    <div class="flex justify-center">
                      <img width="70%" :src="viewItem.img" />
                    </div>
                    <div
                      class="text-3xl text-main-text uppercase font-bold tracking-widest"
                    >
                      {{ viewItem.title }}
                    </div>
                    <div
                      class="flex items-center justify-between py-5 px-3 w-full"
                    >
                      <Link
                        class="text-base uppercase text-main-text font-semibold tracking-widest border border-main-text rounded-md bg-white px-4 py-2 hover:bg-main-text hover:text-bg-header"
                        href="#"
                        >подробней</Link
                      >
                      <SecondaryButton @click="closeModal">
                        закрыть
                      </SecondaryButton>
                    </div>
                  </div>
                </Modal>
              </swiper-slide>
            </Swiper>

            <div class="absolute top-[44%] left-7"></div>
            <div class="absolute top-[44%] right-7"></div>
          </div>
        </div>
      </section>
      <div class="w-full h-8"></div>
      <section class="hit">
        <div class="w-full flex flex-col items-center justify-center">
          <h1 class="text-main-text uppercase font-bold h1_hit">хиты продаж</h1>
          <div class="w-full h-8 border-t-2 border-main-text"></div>
          <div
            class="hit_slider_box w-full relative bg-white py-5 flex items-center border-4 rounded-xl border-main-text"
          >
            <Swiper
              :navigation="true"
              :modules="modules"
              :breakpoints="{
                1200: { slidesPerView: 3 },
                768: { slidesPerView: 2 },
                700: { slidersPerView: 1 },
              }"
            >
              <swiper-slide
                v-for="(img, idx) in swiperImg"
                :key="idx"
                class="hit_product"
              >
                <Link
                  href="#"
                  class="flex flex-col items-center justify-center relative w-[280px]"
                >
                  <img :src="img.img" width="280" />
                  <span
                    class="mt-12 text-lg uppercase text-main-text font-bold"
                    >{{ img.title }}</span
                  >
                </Link>
                <div
                  class="popup absolute bottom-9 z-50 hover:cursor-pointer"
                  @click="quickView(img)"
                >
                  быстрый просмотр
                </div>
                <Modal
                  :maxWidth="`modalProduct`"
                  :show="openView"
                  :img="img.img"
                  @close="closeModal"
                >
                  <div
                    class="w-full h-full bg-white p-4 flex flex-col items-center justify-between"
                  >
                    <div class="flex justify-center">
                      <img width="70%" :src="viewItem.img" />
                    </div>
                    <div
                      class="text-3xl text-main-text uppercase font-bold tracking-widest"
                    >
                      {{ viewItem.title }}
                    </div>
                    <div
                      class="flex items-center justify-between py-5 px-3 w-full"
                    >
                      <Link
                        class="text-base uppercase text-main-text font-semibold tracking-widest border border-main-text rounded-md bg-white px-4 py-2 hover:bg-main-text hover:text-bg-header"
                        href="#"
                        >подробней</Link
                      >
                      <SecondaryButton @click="closeModal">
                        закрыть
                      </SecondaryButton>
                    </div>
                  </div>
                </Modal>
              </swiper-slide>
            </Swiper>
            <div class="absolute top-[44%] left-7"></div>
            <div class="absolute top-[44%] right-7"></div>
          </div>
        </div>
      </section>
      <div class="w-full h-8"></div>
      <section class="collection">
        <div class="w-full flex flex-col items-center justify-center">
          <h1 class="text-main-text uppercase font-bold h1_hit">коллекции</h1>
          <div class="w-full h-8 border-t-2 border-main-text"></div>
          <div
            class="w-full relative bg-white p-5 flex flex-col items-center border-4 rounded-xl border-main-text"
          >
            <div class="flex flex-wrap items-stretch justify-between w-full">
              <div class="flex flex-col items-center">
                <Link href="#" class="flex flex-col items-center">
                  <img src="../../images/rosessite.jpg" class="flower" />
                </Link>
                <Link
                  href="#"
                  class="flex mt-4 text-lg uppercase text-main-text font-semibold hover:underline"
                  >ассорти "цветы"</Link
                >
              </div>
              <div class="flex flex-col items-center">
                <Link href="#" class="flex flex-col items-center">
                  <img src="../../images/angel108site.jpg" class="angel" />
                </Link>
                <Link
                  href="#"
                  class="flex mt-4 text-lg uppercase text-main-text font-semibold hover:underline"
                  >ассорти "ангелы"</Link
                >
              </div>
              <div class="flex flex-col items-center">
                <Link href="#" class="flex flex-col items-center">
                  <img src="../../images/premiumpinksite.jpg" class="premium" />
                </Link>
                <Link
                  href="#"
                  class="flex mt-4 text-lg uppercase text-main-text font-semibold hover:underline"
                  >ассорти "премиум"</Link
                >
              </div>
              <div class="flex flex-col items-center">
                <Link href="#" class="">
                  <img
                    src="../../images/butterfly108site.jpg"
                    class="butterfly"
                  />
                </Link>
                <Link
                  href="#"
                  class="flex mt-4 text-lg uppercase text-main-text font-semibold hover:underline"
                  >ассорти "бабочки"</Link
                >
              </div>
            </div>
          </div>
        </div>
      </section>
      <div class="w-full h-8"></div>
      <div class="flex w-full justify-center">
        <Link
          href="#"
          class="border border-main-text bg-main-text py-2 px-4 rounded-lg text-base uppercase text-bg-header hover:bg-bg-header hover:text-main-text"
        >
          перейти в каталог
        </Link>
      </div>
      <div class="w-full h-8"></div>
    </div>
  </MainLayout>
</template>

<style scoped>
.wrapper {
  min-height: 100vh;
  background: linear-gradient(
    180deg,
    var(--bg-header) 0%,
    rgba(234, 211, 196, 0.768) 90%
  );
}
.slider {
  background-image: url(../../images/slide1.jpg);
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
  width: 100%;
  height: 100%;
  animation: animate 30s infinite;
}

.swiper-slide {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 377px;
}

.img_new {
  max-height: 220px;
}

.flower,
.premium {
  flex-basis: auto;
  max-height: 197px;
}

.angel,
.butterfly {
  flex-basis: auto;
  max-height: 197px;
}

@keyframes animate {
  15% {
    background-image: url(../../images/slide2.jpg);
    background-size: contain;
    background-repeat: no-repeat;
  }
  30% {
    background-image: url(../../images/slide3.jpg);
    background-size: contain;
    background-repeat: no-repeat;
  }
  45% {
    background-image: url(../../images/slide4.jpg);
    background-size: contain;
    background-repeat: no-repeat;
  }
  60% {
    background-image: url(../../images/slide5.jpg);
    background-size: contain;
    background-repeat: no-repeat;
  }
  75% {
    background-image: url(../../images/slide6.jpg);
    background-size: contain;
    background-repeat: no-repeat;
  }
  100% {
    background-image: url(../../images/slide1.jpg);
    background-size: contain;
    background-repeat: no-repeat;
  }
}
</style>