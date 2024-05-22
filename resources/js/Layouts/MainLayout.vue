<script setup>
import { Link } from "@inertiajs/vue3";
import Dropdown from "@/Components/Dropdown.vue";
import Details from "@/Components/Details.vue";
</script>

<template>
  <header>
    <div class="header">
      <div class="header_box center">
        <div class="header_lef">
          <Link href="#">
            <img class="logo" src="../../images/logo.png" alt="Logo" />
          </Link>
        </div>
        <div class="header_center">
          <span class="slogan">&laquo;Вдохновение в традициях!&raquo;</span>
        </div>
        <div class="header_right">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-6 h-6"
            style="color: var(--main-text)"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 0 0 2.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 0 1-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 0 0-1.091-.852H4.5A2.25 2.25 0 0 0 2.25 4.5v2.25Z"
            />
          </svg>
          <span class="phone">(495) 280-36-81</span>
        </div>
        <div class="drop hidden">
          <Dropdown>
            <template #trigger>
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="w-6 h-6"
                style="color: var(--main-text)"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
                />
              </svg>
            </template>
            <template #content>
              <div class="flex flex-col">
                <div class="pl-4 py-4">
                  <ul>
                    <li class="mb-4">
                      <Link
                        href="#"
                        class="text-base uppercase tracking-wider py-4"
                        style="color: var(--bg-header)"
                      >
                        О компании
                      </Link>
                    </li>
                    <li class="mb-4">
                      <div class="flex items-center">
                        <Details
                          :title="`продукция`"
                          :detail="`detail`"
                          :summary="`s-summary`"
                          :page="`drop`"
                        >
                          <ul
                            class="w-full ml-[-14px] mt-2 pl-6 py-3"
                            style="background-color: var(--bg-header)"
                          >
                            <li class="my-3">
                              <Link
                                href="#"
                                class="text-sm uppercase"
                                style="color: var(--main-text)"
                                >весовые конфеты</Link
                              >
                            </li>
                            <li class="my-3">
                              <Link
                                href="#"
                                class="text-sm uppercase"
                                style="color: var(--main-text)"
                                >коробочные конфеты</Link
                              >
                            </li>
                            <li class="my-3">
                              <Link
                                href="#"
                                class="text-sm uppercase"
                                style="color: var(--main-text)"
                                >желейные конфеты</Link
                              >
                            </li>
                            <li class="my-3">
                              <Link
                                href="#"
                                class="text-sm uppercase"
                                style="color: var(--main-text)"
                                >новый год</Link
                              >
                            </li>
                            <li class="my-3">
                              <Link
                                href="#"
                                class="text-sm uppercase"
                                style="color: var(--main-text)"
                                >новинки</Link
                              >
                            </li>
                          </ul>
                        </Details>
                      </div>
                    </li>
                    <li class="mb-4">
                      <Link
                        href="#"
                        class="text-base uppercase tracking-wider py-4"
                        style="color: var(--bg-header)"
                      >
                        вопрос-ответ
                      </Link>
                    </li>
                    <li class="mb-4">
                      <Link
                        href="#"
                        class="text-base uppercase tracking-wider py-4"
                        style="color: var(--bg-header)"
                      >
                        контакты
                      </Link>
                    </li>
                  </ul>
                </div>
              </div>
            </template>
          </Dropdown>
        </div>
      </div>
    </div>
  </header>
  <nav>
    <div class="nav">
      <ul class="menu center">
        <li class="list">
          <Link href="#" class="link"> О компании </Link>
        </li>
        <li class="list">
          <Link href="#" class="link product_menu"> продукция </Link>
          <ul class="product_drop_menu absolute top-10 w-[220px] p-2 z-50">
            <li class="flex items-center justify-start h-7 m-2">
              <Link href="#" class="product_drop_menu_link text-sm uppercase"
                >весовые конфеты</Link
              >
            </li>
            <li class="flex items-center justify-start h-7 m-2">
              <Link href="#" class="product_drop_menu_link text-sm uppercase"
                >коробочные конфеты</Link
              >
            </li>
            <li class="flex items-center justify-start h-7 m-2">
              <Link href="#" class="product_drop_menu_link text-sm uppercase"
                >желейные конфеты</Link
              >
            </li>
            <li class="flex items-center justify-start h-7 m-2">
              <Link href="#" class="product_drop_menu_link text-sm uppercase"
                >новый год</Link
              >
            </li>
            <li class="flex items-center justify-start h-7 m-2">
              <Link href="#" class="product_drop_menu_link text-sm uppercase"
                >новинки</Link
              >
            </li>
          </ul>
        </li>
        <li class="list">
          <Link href="#" class="link"> вопрос-ответ </Link>
        </li>
        <li class="list">
          <Link href="#" class="link"> контакты </Link>
        </li>
      </ul>
    </div>
  </nav>
  <slot></slot>
  <footer>
    <div class="footer center w-screen flex items-start justify-between">
      <div class="footer_logo py-4">
        <Link href="#">
          <img class="logo" src="../../images/logo.png" alt="Logo" />
        </Link>
      </div>
      <div class="footer-content">
        <h3 class="footer-h3">Связаться с нами</h3>
        <div class="footer-phone">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-4 h-4 mr-2"
            style="color: var(--main-text)"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 0 0 2.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 0 1-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 0 0-1.091-.852H4.5A2.25 2.25 0 0 0 2.25 4.5v2.25Z"
            />
          </svg>
          <span class="footer-style">(495) 280-36-81</span>
        </div>
        <div class="footer-phone">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-4 h-4 mr-2"
            style="color: var(--main-text)"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75"
            />
          </svg>
          <span class="footer-style">127106, город Москва, а/я 4</span>
        </div>
        <div class="footer-phone">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-4 h-4 mr-2"
            style="color: var(--main-text)"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M16.5 12a4.5 4.5 0 1 1-9 0 4.5 4.5 0 0 1 9 0Zm0 0c0 1.657 1.007 3 2.25 3S21 13.657 21 12a9 9 0 1 0-2.636 6.364M16.5 12V8.25"
            />
          </svg>
          <span class="footer-style">info@kfsp.ru</span>
        </div>
      </div>
      <div class="footer-content">
        <h3 class="footer-h3">О компании</h3>
        <ul>
          <li>
            <Link href="#" class="footer-style">Контакты</Link>
          </li>
          <li>
            <Link href="#" class="footer-style">Новости</Link>
          </li>
          <li>
            <Link href="#" class="footer-style">Схема проезда</Link>
          </li>
          <li>
            <Link href="#" class="footer-style">О компании</Link>
          </li>
          <li>
            <Link href="#" class="footer-style">Работа у нас</Link>
          </li>
        </ul>
      </div>
    </div>
  </footer>
</template>

<style scoped>
</style>