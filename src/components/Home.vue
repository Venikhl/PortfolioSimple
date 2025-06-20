<script>
export default {
  data() {
    return {
      words: ["Designer", "Full-stack Developer", "Web Developer"],
      currentWordIndex: 0,
      isMobileNavActive: false,
      isNavbarExpanded: false,
      activeSection: 'hero'
    };
  },
  mounted() {
    this.changeWord();
    window.addEventListener('scroll', this.onScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.onScroll);
  },
  methods: {
    changeWord() {
      setInterval(() => {
        this.currentWordIndex = (this.currentWordIndex + 1) % this.words.length;
      }, 2000);
    },
    toggleMobileNav() {
      this.isMobileNavActive = !this.isMobileNavActive;
    },
    expandNavbar() {
      this.isNavbarExpanded = true;
    },
    collapseNavbar() {
      this.isNavbarExpanded = false;
    },
    onScroll() {
      const sections = ['hero', 'about', 'resume', 'portfolio'];
      let found = 'hero';
      for (let id of sections) {
        const el = document.getElementById(id);
        if (el) {
          const rect = el.getBoundingClientRect();
          if (rect.top <= 100 && rect.bottom > 100) {
            found = id;
            break;
          }
        }
      }
      this.activeSection = found;
    }
  },
  props: {
    diplomaSTEP2: String,
    IELTS: String,
    TarotApp: String,
    InnoSchedule: String,
    StoryMarks: String,
    diplomaSTEP1: String,
    STEP: String,
    ELAB: String,
    bebras: String,
    innobot: String,
    Cocktail: String,
    JobSearch: String,
    AglayaBot: String
  }
}
</script>



<template>
   <!-- ======= Mobile nav toggle button ======= -->
   <i class="bi bi-list mobile-nav-toggle d-lg-none" @click="toggleMobileNav"></i>
  <ul v-if="isMobileNavActive" class="mobile-nav-menu">
    <li>
      <a
        href="#hero"
        class="nav-link scrollto"
        :class="{ active: activeSection === 'hero' }"
      >Главная</a>
    </li>
    <li>
      <a
        href="#about"
        class="nav-link scrollto"
        :class="{ active: activeSection === 'about' }"
      >Обо мне</a>
    </li>
    <li>
      <a
        href="#resume"
        class="nav-link scrollto"
        :class="{ active: activeSection === 'resume' }"
      >Резюме</a>
    </li>
    <li>
      <a
        href="#portfolio"
        class="nav-link scrollto"
        :class="{ active: activeSection === 'portfolio' }"
      >Портфолио</a>
    </li>
  </ul>
  <!-- ======= Header ======= -->
  <header id="header" class="d-flex flex-column justify-content-center">
    <nav
      id="navbar"
      class="navbar nav-menu"
      :class="{ expanded: isNavbarExpanded }"
      @mouseenter="expandNavbar"
      @mouseleave="collapseNavbar"
    >
      <ul>
        <li>
          <a
            href="#hero"
            class="nav-link scrollto"
            :class="{ active: activeSection === 'hero' }"
          >
            <i class="bx bx-home"></i> <span>Главная</span>
          </a>
        </li>
        <li>
          <a
            href="#about"
            class="nav-link scrollto"
            :class="{ active: activeSection === 'about' }"
          >
            <i class="bx bx-user"></i> <span>Обо мне</span>
          </a>
        </li>
        <li>
          <a
            href="#resume"
            class="nav-link scrollto"
            :class="{ active: activeSection === 'resume' }"
          >
            <i class="bx bx-file-blank"></i> <span>Резюме</span>
          </a>
        </li>
        <li>
          <a
            href="#portfolio"
            class="nav-link scrollto"
            :class="{ active: activeSection === 'portfolio' }"
          >
            <i class="bx bx-book-content"></i> <span>Портфолио</span>
          </a>
        </li>
      </ul>
    </nav>
  </header>

  <!-- ======= Hero Section ======= -->
 <section id="hero">
    <!-- Бесконечный фон текста -->
    <div class="portfolio-bg-text">
      <div v-for="n in 20" :key="n">PORTFOLIO PORTFOLIO PORTFOLIO PORTFOLIO</div>
    </div>

    <!-- Стеклянный блок с текстом -->
    <div class="glass" data-aos="zoom-in" data-aos-delay="100">
      <h1>Павлов Глеб</h1>
      <p>Я <span class="typed">{{ words[currentWordIndex] }}</span></p>
      <div class="social-links">
        <a href="https://www.instagram.com/venikhl/" class="instagram"><i class="bx bxl-instagram"></i></a>
        <a href="https://t.me/venikhl" class="telegram"><i class="bx bxl-telegram"></i></a>
      </div>
    </div>
  </section>


  <main id="main">

    <!-- ======= About Section ======= -->
    <section id="about" class="about">
      <div class="container" data-aos="fade-up">

        <div class="section-title">
          <h2>Обо мне</h2>
          <p>Привет! Я Глеб — фронтенд-разработчик с опытом создания продуктов на Vue, React и TypeScript. Работал над интерфейсами от идеи до продакшна, участвовал в проектировании архитектуры, взаимодействии с аналитикой и бэкендом. Стараюсь смотреть на задачу шире кода и фокусироваться на продуктовой ценности.</p>
        </div>

        <div class="row">
          <div class="col-lg-4">
            <img src="../assets/img/profile_img.jpg" class="img-fluid" alt="">
          </div>
          <div class="col-lg-8 pt-4 pt-lg-0 content">
            <h3>UI/UX Дизайнер &amp; Web Разработчик.</h3>
            <p class="fst-italic">
              В настоящее время я учусь на 4 курсе Университета Иннополис по специальности «Информатика и вычислительная техника»
            </p>
            <div class="row">
              <div class="col-lg-6">
                <ul>
                  <li><i class="bi bi-chevron-right"></i> <strong>Дата рождения:</strong> <span>10 ноября 2004</span></li>
                  <li><i class="bi bi-chevron-right"></i> <strong>Телефон:</strong> <span>+7 953 834 12 12</span></li>
                  <li><i class="bi bi-chevron-right"></i> <strong>Город:</strong> <span>Россия, Иннополис</span></li>
                  </ul>
                  </div>
                  <div class="col-lg-6">
                  <ul>
                  <li><i class="bi bi-chevron-right"></i> <strong>Возраст:</strong> <span>20</span></li>
                  <li><i class="bi bi-chevron-right"></i> <strong>Степень:</strong> <span>Бакалавр</span></li>
                  <li><i class="bi bi-chevron-right"></i> <strong>Email:</strong> <span>g.o.pavlov2019@gmail.com</span></li>
                  <li><i class="bi bi-chevron-right"></i> <strong>Фриланс:</strong> <span>Доступен</span></li>
                </ul>
              </div>
            </div>
            <p>
              У меня свободный график, поэтому готов работать на полной занятости в режиме 5/2.
            </p>
          </div>
        </div>

      </div>
    </section><!-- End About Section -->

    <!-- ======= Resume Section ======= -->
<section id="resume" class="resume">
  <div class="container" data-aos="fade-up">

    <div class="section-title">
  <h2>Резюме</h2>
  <p>Разрабатываю интерфейсы, которые не только выглядят, но и работают: стабильно, понятно и удобно. Привык быстро вливаться в команду, брать ответственность и глубоко разбираться в логике проекта. Всегда готов к вызовам и уверен в своих навыках.</p>
</div>

  <div class="row">
    <div class="col-lg-6">
      <h3 class="resume-title">Обзор</h3>
      <div class="resume-item pb-0">
        <h4>Павлов Глеб</h4>
        <p><em>Я подхожу к каждой задаче с энтузиазмом и искренней страстью к тому, что я делаю. Обратная связь и правки всегда приветствуются; я воспринимаю их как возможность для роста и улучшения своей работы.</em></p>
        <ul>
          <li>Россия, Иннополис</li>
          <li>+7 953 834 12 12</li>
          <li>g.o.pavlov2019@gmail.com</li>
        </ul>
      </div>
      <h3 class="resume-title">Бакалавриат</h3>
      <div class="resume-item">
        <h4>2022 - 2025</h4>
        <p><em>Университет Иннополис, Россия, Татарстан</em></p>
        <p>Факультет: Факультет компьютерных и инженерных наук</p>
        <p>Специальность: Информатика и вычислительная техника</p>
        <p>Направление: Анализ данных и Искусственный интеллект</p>
      </div>
    </div>
    <div class="col-lg-6">
      <h3 class="resume-title">Образование</h3>
      <div class="resume-item">
        <h4>ITStep Academy</h4>
        <h5>2018 - 2022</h5>
        <p><em>Казахстан, Алматы</em></p>
        <p><strong>Я развил разнообразные навыки и накопил обширные знания в различных областях, включая:</strong></p>
        <ul class="skills-list">
          <li>Основы информационных технологий</li>
          <li>Программирование на C</li>
          <li>Объектно-ориентированное программирование (C++)</li>
          <li>Теория баз данных</li>
          <li>MS SQL Server</li>
          <li>Веб-разработка (HTML5, CSS3, JS)</li>
          <li>Разработка игр (Unity)</li>
          <li>Разработка десктопных приложений (WPF)</li>
          <li>Веб-технологии (ASP.NET AJAX)</li>
          <li>UML</li>
          <li>Java</li>
          <li>Python</li>
          <li>PHP</li>
          <li>Frontend Frameworks (Vue.js, React)</li>
        </ul>
        <p>Эти области позволили мне участвовать в различных проектах, хакатонах и задачах что способствовало расширению моего опыта.</p>
      </div>
    </div>
  </div>
</div>
</section>
    <!-- ======= Раздел Портфолио ======= -->
<section id="portfolio" class="portfolio section-bg">
  <div class="container" data-aos="fade-up">

    <div class="section-title">
      <h2>Портфолио</h2>
      <p>В этом портфолио вы найдете список моих профессиональных и академических достижений, проектов и работ.</p>
    </div>

    <div class="row">
      <div class="col-lg-12 d-flex justify-content-center" data-aos="fade-up" data-aos-delay="100">
        <ul id="portfolio-flters">
          <li data-filter="*" class="filter-active">Все</li>
          <li data-filter=".filter-app">Работы</li>
          <li data-filter=".filter-diploma">Дипломы</li>
          <li data-filter=".filter-web">Веб</li>
        </ul>
      </div>
    </div>

    <div class="row portfolio-container" data-aos="fade-up" data-aos-delay="200">

      <div class="col-lg-4 col-md-6 portfolio-item filter-diploma">
        <div class="portfolio-wrap">
          <img :src="diplomaSTEP1" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>Диплом ITStep.</h4>
            <p>Диплом</p>
            <div class="portfolio-links">
              <a :href="diplomaSTEP1" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Диплом 1" target="_blank"><i class="bx bx-plus"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-diploma">
        <div class="portfolio-wrap">
          <img :src="ELAB" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>Диплом ELAB.Asia.</h4>
            <p>Диплом</p>
            <div class="portfolio-links">
              <a :href="ELAB" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Диплом 1" target="_blank"><i class="bx bx-plus"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-diploma">
        <div class="portfolio-wrap">
          <img :src="STEP" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>Диплом хакатона ITStep.</h4>
            <p>Диплом</p>
            <div class="portfolio-links">
              <a :href="STEP" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Диплом 1" target="_blank"><i class="bx bx-plus"></i></a>
            </div>
          </div>
        </div>
      </div>
      
      <div class="col-lg-4 col-md-6 portfolio-item filter-diploma">
        <div class="portfolio-wrap">
          <img :src="bebras" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>Диплом BEBRAS.</h4>
            <p>Диплом</p>
            <div class="portfolio-links">
              <a :href="bebras" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Диплом 1" target="_blank"><i class="bx bx-plus"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-diploma">
        <div class="portfolio-wrap">
          <img :src="diplomaSTEP2" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>Пройденные курсы ITStep.</h4>
            <p>Диплом</p>
            <div class="portfolio-links">
              <a :href="diplomaSTEP2" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Диплом 2" target="_blank"><i class="bx bx-plus"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-diploma">
        <div class="portfolio-wrap">
          <img :src="IELTS" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>Диплом IELTS.</h4>
            <p>Диплом</p>
            <div class="portfolio-links">
              <a :href="IELTS" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Диплом 2" target="_blank"><i class="bx bx-plus"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-app">
        <div class="portfolio-wrap">
          <img :src="AglayaBot" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>AglayaBot - телеграм бот для управления всей компанией через локальный ИИ.</h4>
            <p>Приложение</p>
            <div class="portfolio-links">
              <a :href="AglayaBot" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Приложение 3" target="_blank"><i class="bx bx-plus"></i></a>
              <a href="https://drive.google.com/file/d/1fjYvWQoMqoa0jL173P-joOd6mVtt-ilT/view?usp=drive_link" class="portfolio-details-lightbox" data-glightbox="type: external" title="Детали портфолио"><i class="bx bx-link"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-app">
        <div class="portfolio-wrap">
          <img :src="Cocktail" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>Sign-ature Cocktail - Компьютерная игра где вы можете управлять руками персонажа, как своими через камеру.</h4>
            <p>Приложение</p>
            <div class="portfolio-links">
              <a :href="Cocktail" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Приложение 2" target="_blank"><i class="bx bx-plus"></i></a>
              <a href="https://a-walking-mess.itch.io/sign-ature-cocktail" class="portfolio-details-lightbox" data-glightbox="type: external" title="Детали портфолио"><i class="bx bx-plus"></i></a>
              <a href="https://drive.google.com/file/d/1LhJ7cjRZ1KN2wLlLCO9LsZSM3f0b3fYD/view?clckid=25ce10c2" class="portfolio-details-lightbox" data-glightbox="type: external" title="Детали портфолио"><i class="bx bx-link"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-app">
        <div class="portfolio-wrap">
          <img :src="TarotApp" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>TarotApp - приложение для гадания на картах Таро.</h4>
            <p>Приложение</p>
            <div class="portfolio-links">
              <a :href="TarotApp" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Приложение 3" target="_blank"><i class="bx bx-plus"></i></a>
              <a href="https://github.com/Venikhl/Tarot" class="portfolio-details-lightbox" data-glightbox="type: external" title="Детали портфолио"><i class="bx bx-link"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-app">
        <div class="portfolio-wrap">
          <img :src="innobot" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>InnoScheduleBot - Бот для расписания студентов Иннополиса.</h4>
            <p>Приложение</p>
            <div class="portfolio-links">
              <a :href="innobot" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Приложение 1" target="_blank"><i class="bx bx-plus"></i></a>
              <a href="https://t.me/Inno_schedule_bot" class="portfolio-details-lightbox" data-glightbox="type: external" title="Детали портфолио"><i class="bx bx-link"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-web">
        <div class="portfolio-wrap">
          <img :src="JobSearch" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>РаботаПоиск - сайт для поиска подходящих вакансий и резюме.</h4>
            <p>Веб</p>
            <div class="portfolio-links">
              <a :href="JobSearch" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Веб 4" target="_blank"><i class="bx bx-plus"></i></a>
              <a href="https://github.com/Venikhl/vacancy-aggregator.git" class="portfolio-details-lightbox" data-glightbox="type: external" title="Детали портфолио"><i class="bx bx-link"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-web">
        <div class="portfolio-wrap">
          <img :src="InnoSchedule" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>InnoSchedule - сайт для студентов Иннополиса.</h4>
            <p>Веб</p>
            <div class="portfolio-links">
              <a :href="InnoSchedule" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Веб 3" target="_blank"><i class="bx bx-plus"></i></a>
              <a href="https://master--flourishing-kataifi-ec68d1.netlify.app" class="portfolio-details-lightbox" data-glightbox="type: external" title="Детали портфолио"><i class="bx bx-link"></i></a>
            </div>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-6 portfolio-item filter-web">
        <div class="portfolio-wrap">
          <img :src="StoryMarks" class="img-fluid" alt="">
          <div class="portfolio-info">
            <h4>StoryMarks - сайт для сохранения прогресса чтения и просмотра.</h4>
            <p>Веб</p>
            <div class="portfolio-links">
              <a :href="StoryMarks" data-gallery="portfolioGallery" class="portfolio-lightbox" title="Веб 3" target="_blank"><i class="bx bx-plus"></i></a>
              <a href="https://disk.yandex.ru/i/rccSZRtVxLEYKQ" class="portfolio-details-lightbox" data-glightbox="type: external" title="Детали портфолио"><i class="bx bx-link"></i></a>
            </div>
          </div>
        </div>
      </div>
    </div>

  </div>
</section><!-- Конец раздела Портфолио -->

</main><!-- Конец #main -->
</template>