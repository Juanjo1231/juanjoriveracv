<template lang="pug">
.container.main
  .row.main
    #personal_l.col.s12.m5.l4.show-on-large
      .row.header.card
        .tag
          i.hide-on-med-and-down.fa.fa-desktop.fa-2x
          i.hide-on-small-only.hide-on-large-only.fa.fa-tablet.fa-2x
          i.hide-on-med-and-up.fa.fa-mobile.fa-2x
        .avatar
          img(src="https://profile.actionsprout.com/default.jpeg")
        h4 Juan José Rivera
        h5 Desarrollador Javascript
      
      .row.card
        i.material-icons.tag person
        .col.s10.offset-s2 Juan José Rivera Román
        .col.s10.offset-s2 Guatemalteco
        .col.s10.offset-s2 2093 47562 0101
      .row.card
        i.material-icons.tag mode_comment
        .col.s10.offset-s2 juanjoriverar@gmail.com
        .col.s10.offset-s2 4137 1726
      .row.card
        i.material-icons.tag language
        .col.s10.offset-s2 Español
        .col.s10.offset-s2.material-icons star star star star star
        .col.s10.offset-s2 Inglés
        .col.s10.offset-s2.material-icons star star star star_half star_border
        .col.s10.offset-s2 Francés
        .col.s10.offset-s2.material-icons star star_border star_border star_border star_border
      .row.card
        i.material-icons.tag people
        a.col.s1.offset-s2.fa.fa-facebook-official.fa-2x(href='https://www.facebook.com/Juanjo.Formiga' target='_blank')
        a.col.s1.offset-s1.fa.fa-codepen.fa-2x(href='https://codepen.io/JuanjoVlado/' target='_blank')
        a.col.s1.offset-s1.fa.fa-github.fa-2x(href='https://github.com/Juanjo1231' target='_blank')
    #prof.col.s12.m7.l8
      .row.card
        .col.s12
          h5.tag Cualidades
        attr(v-for='attr in attrs' v-bind:attr='attr' v-bind:key='attr.id')
      .row.card.center-align
        .col.s12
          h5.tag Habilidades
        skill.col.s4(v-for='skill in skills' v-bind:skill='skill' v-bind:style=`buildStyles(skill)` v-bind:key='skill.id')
        secSkill(v-for="secSkill in secSkills" v-bind:secSkill="secSkill" v-bind:key="secSkill.id")

      .row.card
        .col.s12
          h5.tag Experiencia
        job(v-for='job in jobs' v-bind:job='job' v-bind:key='job.id')

      .row.card
        .col.s12
          h5.tag Referencias
        reffer(v-for="lnk in lnks" v-bind:lnk='lnk' v-bind:key='lnk.id')

</template>

<script>
import Skill from './components/Skill'
import Job from './components/Job'
import Attr from './components/Attribute'
import Reffer from './components/Reffers'
import SecSkill from './components/SecSkill'


export default {
  name: 'app',
  data() {
    return {
      skills: [
        {id: 0, image: 'https://juanjo1231.github.io/juanjoriveracv/dist/html.png', progress: 65},
        {id: 1, image: 'https://juanjo1231.github.io/juanjoriveracv/dist/css.png', progress: 50},
        {id: 2, image: 'https://juanjo1231.github.io/juanjoriveracv/dist/js.png', progress: 40}
      ],
      secSkills: [
        {id: 'sk-0',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/vue.png', text: 'Vue.js'},
        {id: 'sk-1',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/babel.png', text: 'Babel.js'},
        {id: 'sk-2',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/bootsrap.png', text: 'Bootstrap.css'},
        {id: 'sk-3',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/browserify.png', text: 'Browserify'},
        {id: 'sk-4',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/java.png', text: 'Java SE'},
        {id: 'sk-5',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/node.png', text: 'Node.js'},
        {id: 'sk-6',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/mysql.png', text: 'MySql'},
        {id: 'sk-7',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/php.png', text: 'PHP'},
        {id: 'sk-8',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/stylus.png', text: 'Stylus'},
        {id: 'sk-9',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/materialize.png', text: 'Materialize.css'},
        {id: 'sk-10',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/sass.png', text: 'Sass.css'},
        {id: 'sk-11',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/gulp.png', text: 'Gulp'},
        {id: 'sk-12',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/googleappscript.png', text: 'Google App Script'},
        {id: 'sk-13',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/npm.png', text: 'npm'},
        {id: 'sk-14',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/platzi.png', text: 'Platzi.com'},
        {id: 'sk-15',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/ubuntu.png', text: 'Ubuntu'},
        {id: 'sk-16',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/webpack.png', text: 'Webpack'},
        {id: 'sk-17',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/spring.png', text: 'Spring Tool Suite'},
        {id: 'sk-18',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/sublime.png', text: 'Sublime Text'},
        {id: 'sk-19',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/eclipse.png', text: 'Eclipse'},
        {id: 'sk-20',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/excel.png', text: 'Excel VBA'},
        {id: 'sk-21',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/git.png', text: 'Git'},
        {id: 'sk-22',image: 'https://juanjo1231.github.io/juanjoriveracv/dist/visualstudio.png', text: 'Visual Studio'},
      ],
      jobs: [
        {
          id: 'jb-0',
          company: 'Allied Global',
          date: '2012 - 2014',
          positions: [
            {
              id: 'ag-0',
              name:'Agente telefónico',
              tasks: [
                {id:"ag-tsk-0", value: "Recibir llamadas en inglés y español"},
                {id:"ag-tsk-1", value: "Proveer servicio técnico e información specifica de servicios"}
              ]
            }
          ]
        },
        {
          id: 'jb-1',
          company: 'Innovative Contact Solutions',
          date: '2014 - 2017',
          positions: [
            {
              id: 'ics-0',
              name:'Email and Chat CSR',
              tasks: [
                {id:"ics-tsk-0", value: "Recibir y enviar emails y chats en inglés y español"},
                {id:"ics-tsk-1", value: "Contactar proveedores y servicios de entrega por email, chat o teléfono"},
              ]
            },
            {
              id: 'ics-1',
              name:'Analista de Workforce',
              tasks: [
                {id:"ics-tsk-2", value: "Reunir datos del área de producción"},
                {id:"ics-tsk-3", value: "Analisis de datos"},
                {id:"ics-tsk-4", value: "Organizar y presentar datos de manera organizada y precisa"}
              ]
            },
            {
              id: 'ics-2',
              name:'Desarrollador de Workforce',
              tasks: [
                {id:"ics-tsk-2", value: "Desarrollo de herramientas digitales para el departamento y el área de produccion"},
                {id:"ics-tsk-3", value: "Analisis de datos"},
                {id:"ics-tsk-4", value: "Optimización de processos para el departamento y el área de producción"}
              ]
            }
          ]
        }
      ],
      attrs: [
        {id: 'at-0', val: 'Creativo'},
        {id: 'at-1', val: 'Proactivo'},
        {id: 'at-2', val: 'Trabajo en equipo'},
        {id: 'at-3', val: 'Autodidacta'},
        {id: 'at-4', val: 'Perseverante'},
        {id: 'at-5', val: 'Eficiente'}
      ],
      lnks: [
        {
          id: 'lnk-0',
          name: 'Vanessa Urizar',
          title: 'Supervisora',
          fb: 'https://www.facebook.com/vanessa.urizar/about?lst=1281192704%3A729533883%3A1517441025',
          image: 'https://juanjo1231.github.io/juanjoriveracv/dist/vanessa_urizar.png',
          tel: '3097-3800'
        },
        {
          id: 'lnk-1',
          name: 'Luis Diego Castillo',
          title: 'Supervisor',
          fb: 'https://www.facebook.com/luisdiego9',
          image: 'https://juanjo1231.github.io/juanjoriveracv/dist/luis_castillo.png',
          tel: '3040-5164'
        },
        {
          id: 'lnk-2',
          name: 'Luis Capilla',
          title: 'Supervisor',
          fb: 'https://www.facebook.com/thorondor.gwaihir',
          image: 'https://juanjo1231.github.io/juanjoriveracv/dist/luis_capilla.png',
          tel: '5126-5145'
        },
      ]
    }
  },
  components: {
    Skill,
    Job,
    Attr,
    Reffer,
    SecSkill
  },
  methods: {
    buildStyles (skill) {
      return `background-image: url("${skill.image}")`
    }
  }
}
</script>

<style lang="stylus">
$medium = white
$text_on_medium = #5b6774
$strong = #175887
$text_on_strong = white
$prof_strong = #52a4bb
$shadow_1 = 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24)
$shadow_2 = 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23)

html
body
  height 100%
  margin 0
  padding 0
  font-size 16px
  background-color #e9e8e6
  font-family 'Roboto'
  font-weight 500
  color #5b6774
  text-rendering optimizeLegibility
.container
  width 90%
.main
  height 100%
  margin 0 auto
#personal_l
  display flex
  flex-direction column
  position relative
  padding 0.25rem .75rem  
  h4
    font-size 1.4rem
    margin 0 auto
    text-align center
  h5
    font-size 1rem
    margin 0 auto
    text-align center
  .card
    text-align left
    padding 1rem 0
    background-color $medium
    border-radius 1rem 0 0 0
    box-shadow $shadow_1
    color $text_on_medium
    margin 0.5rem 0
    transform translate(0, -100rem)
    animation-name enter
    animation-duration 0.8s
    animation-fill-mode forwards
    &:nth-child(1)
      background-color $strong
      color $text_on_strong
      animation-delay 0.8s
    &:nth-child(2)
      animation-delay 0.6s
    &:nth-child(3)
      animation-delay 0.4s
    &:nth-child(4)
      animation-delay 0.2s
.tag
  position absolute
  top -2px
  left -2px
  padding 0.5rem
  background-color white
  color $strong
  border-radius 1rem 0 0 0
  border 2px solid $strong
  box-shadow $shadow_2
      
#prof
  padding 0 .75rem
  background-color white
  margin-top 0.75rem
  h5
    margin 0
    font-size 1.2rem
  .card
    padding-top 3rem
    position relative
    box-shadow none
    border-bottom 2px solid #ddd
    margin 1rem 0
  .tag
    background-color $prof_strong
    border-color $prof_strong
    color $text_on_strong
  
@keyframes enter
  to
    transform translate(0,0)
    
@media screen and (min-width: 601px)
  #personal_l
    height 100%
@media screen and (max-width: 600px)
  #personal_l
    overflow hidden
    .card
      transform translate(-150%, 0)
      &:nth-child(1)
        animation-delay 0s
      &:nth-child(2)
        animation-delay 0.2s
      &:nth-child(3)
        animation-delay 0.4s
      &:nth-child(4)
        animation-delay 0.6s
      &:last-child
        animation-delay 0.8s
  
/*COMPLEMENTARY*/
.avatar
  img
    height 6rem
    margin 0 auto
    margin-bottom 1rem
    display block
    border-radius 3rem 0
    
a.fa
  color $text_on_medium
  cursor pointer
  transition 0.3s
.fa-facebook-official:hover
  color #3b5998
.fa-codepen:hover
  color black
.fa-github:hover
  color black
.fa-whatsapp:hover
  color #25d366

</style>
