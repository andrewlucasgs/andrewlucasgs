<template>
  <div id="main-wrapper">
    <nav class="navbar navbar-expand-lg navbar-dark side-color fixed-top" id="sideNav">
      <a class="navbar-brand js-scroll-trigger" href="#page-top">
        <span class="d-block d-lg-none">{{ firstName }}</span>
        <span class="d-none d-lg-block">
          <img class="img-fluid img-profile rounded-circle mx-auto mb-2" src="https://avatars1.githubusercontent.com/u/22451668?s=460&v=4" alt="">
        </span>
      </a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#about">{{sections.about}}</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#experience">{{sections.projects}}</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#education">{{sections.education}}</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#skills">{{sections.skills}}</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#interests">{{sections.interests}}</a>
          </li>
          <li class="nav-item">
            <a class="nav-link js-scroll-trigger" href="#awards">{{sections.certifications}}</a>
          </li>
        </ul>
      </div>
    </nav>

    <div class="container-fluid p-0">

      <section class="resume-section p-3 p-lg-5 d-flex d-column" id="about">
        <div class="my-auto">
          <h1 class="mb-0">{{ firstName }}
            <span class="primary-color">{{ lastName }}</span>
          </h1>
          <div class="subheading mb-5 ">{{ address }} · {{ phoneNumber }} ·
            <a class="primary-color" href="mailto:name@email.com">{{ email}}</a>
          </div>
          <p class="lead mb-5">{{ abstract }}</p>
          <div class="social-icons">
            <a href="#">
              <i class="fa fa-linkedin"></i>
            </a>
            <a href="https://github.com/andrewlucasgs">
              <i class="fa fa-github"></i>
            </a>
            <a href="#">
              <i class="fa fa-twitter"></i>
            </a>
            <a href="#">
              <i class="fa fa-facebook-f"></i>
            </a>
          </div>
        </div>
      </section>

      <hr class="m-0">

      <section class="resume-section p-3 p-lg-5 d-flex flex-column" id="experience">
        <div class="my-auto">
          <h2 class="mb-5">{{sections.projects}}</h2>

          <div class="resume-item d-flex flex-column flex-md-row mb-5" v-for="project in projects" :key="project">
            <div class="resume-content mr-auto">
              <a :href="project.repository" id="linkRepository"><h3 class="mb-0">{{project.title}}</h3></a>
              <div v-if="project.description" class="subheading mb-3">{{project.description}}</div>
              <p>{{project.activities}}</p>
              <div v-if="project.technologies">
                <i v-for="technology in project.technologies" :key="technology" :class="['devicon-' + technology + '-plain colored project-technology']"></i>
              </div>
            </div>
            <div class="resume-date text-md-right">
              <span class="text-primary">{{project.startTime}} - {{project.endTime}}</span>
            </div>
          </div>
        </div>

      </section>

      <hr class="m-0">

      <section class="resume-section p-3 p-lg-5 d-flex flex-column" id="education">
        <div class="my-auto">
          <h2 class="mb-5">{{sections.education}}</h2>
          <div class="col-xs-12 col-sm-6 col-md-3">
          
        </div>

          <div class="resume-item d-flex flex-column flex-md-row mb-5" v-for="education in educations" :key="education.local">
            <div class="resume-content mr-auto">
              <h3 class="mb-0">{{education.local}}</h3>
              <div class="subheading mb-3">{{education.course}}</div>
            </div>
            <div class="resume-date text-md-right">
              <span class="text-primary">{{education.startTime}} - {{education.endTime}}</span>
            </div>
          </div>
        </div>
      </section>

      <hr class="m-0">

      <section class="resume-section p-3 p-lg-5 d-flex flex-column" id="skills">
        <div class="my-auto">
          <h2 class="mb-5">{{sections.skills}}</h2>

          <div class="subheading mb-3">Linguagens de Programação &amp; Ferramentas</div>
          <ul class="list-inline dev-icons">
            <li class="list-inline-item" v-for="language in programmingLanguages" :key="language.icon"  >
              <span @mouseover="language.isHover = true" @mouseleave="language.isHover = false">
              <pie-chart 
                :percent="language.level"
                :bar-color="language.color"
                line-cap="butt"
                :line-width=6
                font-size="40"
              >
                <i :class="['devicon-' + language.icon + '-plain', {colored: language.isHover }]"></i>
              </pie-chart>
              </span>
            </li>
          </ul>

          <div class="subheading mb-3">Workflow</div>
          <ul class="fa-ul mb-0">
            <li v-for="item in workflow" :key="item">
              <i class="fa-li fa fa-check"></i>
              {{item}}
            </li>
          </ul>
        </div>
      </section>

      <hr class="m-0">

      <section class="resume-section p-3 p-lg-5 d-flex flex-column" id="interests">
        <div class="my-auto">
          <h2 class="mb-5">{{sections.interests}}</h2>
          <p>{{ interests.resume }}</p>
          <ul class="fa-ul mb-0">
            <li v-for="interest in interests.interests" :key="interest">
              <i class="fa-li fa fa-check"></i>
              {{ interest }}
            </li>
          </ul>
        </div>
      </section>

      <hr class="m-0">

      <section class="resume-section p-3 p-lg-5 d-flex flex-column" id="awards">
        <div class="my-auto">
          <h2 class="mb-5">{{sections.certifications}}</h2>
          <ul class="fa-ul mb-0">
            <li v-for="certification in certifications" :key="certification">
              <i class="fa-li fa fa-trophy text-warning"></i>
              {{ certification }}
              </li>
          </ul>
        </div>
      </section>

    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: "Andrew",
      lastName: "Lucas",
      address: "Planaltina DF / Gama DF",
      email: "andrewlucasgs@gmail.com",
      phoneNumber: "(61) 99248-8395",
      abstract: `
        Oi, eu sou o Andrew. Sou estudante de engenharia de software,
        e sonho em melhorar a vida das pessoas através da tecnologia.
        Sou fascinado por dados e o quanto eles podem nos ensinar, 
        atualmente estou aprimorando meu conhecimento em React Native.
        Busco trabalhos relacionados à Engenharia de Software, com o objetivo de colocar em prática,
        o que estou aprendendo na faculdade, e também aprender coisas novas.
        `,
      projects: [
        {
          title: "ITRAC/UnB",
          repository: "http://itrac.unb.br/",
          description: "Pesquisador Bolsista",
          activities: `Trabalho em parceiria com o Ministério Público, para o levantamento de requisitos para a digitização de serviços públicos`,
          startTime: "Fevereiro 2018",
          endTime: "Presente",
        },
        {
          title: "SiGI-Op",
          repository: "https://github.com/fga-eps-mds/2017.2-SiGI-Op",
          description: "Desenvolvedor",
          activities: `O projeto Sistema de Gerenciamento de Infraestrutura (SiGI) consiste do desenvolvimento de uma aplicação com o objetivo de subsidiar a operação e a gestão da rede GigaCandanga.`,
          startTime: "Agosto 2017",
          endTime: "Dezembro 2017",
          technologies: ["vuejs", "python", "django"]
        },
        {
          title: "TicketFlix",
          repository: "https://github.com/DSW-2018-2/Ticketflix",
          description: "Desenvolvedor",
          activities: `O projeto Ticketflix consiste do desenvolvimento de uma  plataforma de exibição de atrações que estão ou estarão com a compra de ingressos disponíveis.`,
          startTime: "Agosto 2018",
          endTime: "Dezembro 2018",
          technologies: ["python", "django"]
        }
      ],
      interests: {
        resume:
          "Tenho muitos interesses no contexto de tecnologia, mas sou fascinado por:",
        interests: [
          "Ciência de Dados",
          "Chatbots",
          "Desenvolvimento de Web/Mobile",
          "Startup's"
        ]
      },
      certifications: ["Campus Party BSB 2017", "Campus Party BSB 2018"],
      workflow: [
        "Desenvolvimento Mobile/Web",
        "Desenvolvimento Fullstack",
        "Metodologias de desenvolvimento: XP, Scrum, RUP",
        "Inglês: Avançado"
      ],
      programmingLanguages: [
        { icon: "html5", level: 90, color: "#e34c26", isHover: false },
        { icon: "css3", level: 90, color: "#563d7c", isHover: false },
        { icon: "javascript", level: 90, color: "#f1e05a", isHover: false },
        { icon: "python", level: 90, color: "#3572A5", isHover: false },
        { icon: "django", level: 80, color: "#0C3C26", isHover: false },
        { icon: "vuejs", level: 90, color: "#42b983", isHover: false },
        { icon: "nodejs", level: 70, color: "#026e00", isHover: false },
        { icon: "git", level: 95, color: "#f14e32", isHover: false },
        { icon: "github", level: 95, color: "#24292e", isHover: false },
        { icon: "react", level: 70, color: "#61dafb", isHover: false },
        { icon: "docker", level: 70, color: "#0db7ed", isHover: false },
        { icon: "bootstrap", level: 90, color: "#563d7c", isHover: false }
      ],
      educations: [
        {
          local: "UnB",
          course: "Engenharia de Software",
          startTime: "2016",
          endTime: "Presente"
        }
      ],
      sections: {
        about: "sobre",
        projects: "Projetos",
        education: "formação",
        skills: "habilidades",
        interests: "interesses",
        certifications: "certificados"
      }
    };
  },
  mounted() {
    const $ = this.jquery;
    this.$nextTick(() => {
      (function($) {
        // Smooth scrolling using jQuery easing
        $("a.js-scroll-trigger[href*='#']:not([href='#'])").click(function() {
          if (
            location.pathname.replace(/^\//, "") ==
              this.pathname.replace(/^\//, "") &&
            location.hostname == this.hostname
          ) {
            var target = $(this.hash);
            target = target.length
              ? target
              : $("[name=" + this.hash.slice(1) + "]");
            if (target.length) {
              $("html, body").animate(
                {
                  scrollTop: target.offset().top
                },
                1000,
                "easeInOutExpo"
              );
              return false;
            }
          }
        });

        // Closes responsive menu when a scroll trigger link is clicked
        $(".js-scroll-trigger").click(function() {
          $(".navbar-collapse").collapse("hide");
        });

        // Activate scrollspy to add active class to navbar items on scroll
        $("body").scrollspy({
          target: "#sideNav"
        });
      })(jQuery); // End of use strict
    });
  }
};
</script>

<style>
/*!
 * Start Bootstrap - Resume v5.0.2 (https://startbootstrap.com/template-overviews/resume)
 * Copyright 2013-2018 Start Bootstrap
 * Licensed under MIT (https://github.com/BlackrockDigital/startbootstrap-resume/blob/master/LICENSE)
 */

body {
  font-family: "Muli", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji",
    "Segoe UI Symbol", "Noto Color Emoji";
  padding-top: 54px;
  color: #868e96;
}

@media (min-width: 992px) {
  body {
    padding-top: 0;
    padding-left: 17rem;
  }
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Saira Extra Condensed", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji",
    "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-weight: 700;
  text-transform: uppercase;
  color: #343a40;
}

h1 {
  font-size: 6rem;
  line-height: 5.5rem;
}

h2 {
  font-size: 3.5rem;
}

h3 {
  font-size: 2rem;
}

p.lead {
  font-size: 1.15rem;
  font-weight: 400;
}

.subheading {
  text-transform: uppercase;
  font-weight: 500;
  font-family: "Saira Extra Condensed", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji",
    "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-size: 1.5rem;
}

.social-icons a {
  display: inline-block;
  height: 3.5rem;
  width: 3.5rem;
  background-color: #212529;
  color: #fff !important;
  border-radius: 100%;
  text-align: center;
  font-size: 1.5rem;
  line-height: 3.5rem;
  margin-right: 1rem;
}

.social-icons a:last-child {
  margin-right: 0;
}

.social-icons a:hover {
  background-color: #868e96;
}

.dev-icons {
  font-size: 3rem;
}

#sideNav .navbar-nav .nav-item .nav-link {
  font-weight: 800;
  letter-spacing: 0.05rem;
  text-transform: uppercase;
}

#sideNav .navbar-toggler:focus {
  outline-color: #868e96;
}
.side-color {
  background-color: #212529 !important;
}
.primary-color {
  color: #868e96 !important;
}
#linkRepository {
  text-decoration: none;
}

.project-technology{
  font-size: 40px;
  margin-right: 15px;
}
@media (min-width: 992px) {
  #sideNav {
    text-align: center;
    position: fixed;
    top: 0;
    left: 0;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
    width: 17rem;
    height: 100vh;
  }
  #sideNav .navbar-brand {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    margin: auto auto 0;
    padding: 0.5rem;
  }
  #sideNav .navbar-brand .img-profile {
    max-width: 10rem;
    max-height: 10rem;
    border: 0.5rem solid rgba(255, 255, 255, 0.2);
  }
  #sideNav .navbar-collapse {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: start;
    -ms-flex-align: start;
    align-items: flex-start;
    -webkit-box-flex: 0;
    -ms-flex-positive: 0;
    flex-grow: 0;
    width: 100%;
    margin-bottom: auto;
  }
  #sideNav .navbar-collapse .navbar-nav {
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
    width: 100%;
  }
  #sideNav .navbar-collapse .navbar-nav .nav-item {
    display: block;
  }
  #sideNav .navbar-collapse .navbar-nav .nav-item .nav-link {
    display: block;
  }
}

section.resume-section {
  padding-top: 5rem !important;
  padding-bottom: 5rem !important;
  max-width: 75rem;
}

section.resume-section .resume-item .resume-date {
  min-width: none;
}

@media (min-width: 768px) {
  section.resume-section {
    min-height: 100vh;
  }
  section.resume-section .resume-item .resume-date {
    min-width: 18rem;
  }
}

@media (min-width: 992px) {
  section.resume-section {
    padding-top: 3rem !important;
    padding-bottom: 3rem !important;
  }
}

.bg-primary {
  background-color: #bd5d38 !important;
}

.text-primary {
  color: #bd5d38 !important;
}

a {
  color: #bd5d38;
}

a:hover,
a:focus,
a:active {
  color: #824027;
}
</style>
