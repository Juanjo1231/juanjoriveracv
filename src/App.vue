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
        .col.s10.offset-s2 2093 xxxxx xxxx
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
        a.col.s1.offset-s2.fa.fa-facebook-official.fa-2x
        a.col.s1.offset-s1.fa.fa-codepen.fa-2x
        a.col.s1.offset-s1.fa.fa-github.fa-2x
        a.col.s1.offset-s1.fa.fa-whatsapp.fa-2x
    #prof.col.s12.m7.l8
      .row.card
        .col.s12
          h5.tag Cualidades
        .col.s5.offset-s1.qua
          svg.marked
            path.line
          div Cualidad 1
        .col.s5.qua
          svg.marked
            path.line
          div Cualidad 2
        .col.s5.offset-s1.qua
          svg.marked
            path.line
          div Cualidad 3
        .col.s5.qua
          svg.marked
            path.line
          div Cualidad 4
      .row.card
        .col.s12
          h5.tag Habilidades
        .col.s4
          .skill.s-html
            svg.pro
              circle
        .col.s4
          .skill.s-css
            svg.pro
              circle
        .col.s4
          .skill.s-js
            svg.pro
              circle
        .row.carroussel
          .col.s12
      .row.card
        .col.s12
          h5.tag Experiencia
          h6 Allied Global 
            span 2012 - 2014
          .pos-title Agente telefónico
          p.pos-desc Como agente de servicio al cliente bilingüe, tuve la oportunidad de mejorar mi uso del idioma iglés, además de desarrollar habilidades necesarias para tratar con clientes, quienes no siempre estaban contentos, y darle a la situación una solución adecuada. 
        .col.s12
          h6 Innovative Contact Solutions 
            span 2014 - 2017
          .pos-title Email and Chat CSR
          p.pos-desc Al interactuar con clientes de manera escrita, mejoré la lectura y comprensión del idioma inglés, además de la habilidad para brindar soluciones sencillas en menor tiempo. Con el tiempo tambien desempeñé la función de supervisor y capacitador
          .pos-title Analista de Workforce
          p.pos-desc Gracias a mi buen desempeño y actitud, obtuve el puesto de analista para workforce. En aquel entonces, empezé a aprender sobre programación y diseño web, utilicé estos nuevos conocimientos para optimizar procesos en el departamento y tambien para el área de operaciones.
          .pos-title Desarrollador de Workforce
          p.pos-desc Con la creciente necesidad de modernización en los procesos, se me dio la tarea de migrar los antiguos procesos a plataformas más modernas y eficientes, además del desarrollo de herramientas online para facilitar tareas en el área de producción. 
      .row.card
        .col.s12
          h5.tag Hobbies
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      msg: 'Algo'
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

h6
  font-weight bold
  font-size 1.1rem
  span
    font-weight normal
    color $strong
    font-size 0.9rem
    &::before
      content " - "
.pos-title
  font-weight normal
  margin 0
  text-indent 1rem
.pos-desc
  margin 0.3rem 0 1rem 2rem
  font-weight normal
  font-style italic
  
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
  
.marked
  width 35px
  height 35px
  display inline-block
  .line
    fill none
    stroke #00487C
    stroke-width 5
    stroke-linecap round
    stroke-linejoin round
    stroke-dasharray 27
    stroke-dashoffset 27
    d path("M8,20 L15,25 25,10")
    animation-name check
    animation-duration 0.5s
    animation-iteration-count 1
    animation-fill-mode forwards
    animation-timing-function cubic-bezier(0.8, 0, 1, 1)
    animation-delay 0.8s

@keyframes check
  to
    stroke-dashoffset 0
    
.qua
  display flex
  div
    padding-top 0.5rem
  
.skill
  width 6rem
  height 6rem
  background-size 3rem
  background-position center
  background-repeat no-repeat
  border-radius 50%
  margin 1rem auto
  position relative
  &.s-html
    background-image url("https://www.w3.org/html/logo/downloads/HTML5_Logo_512.png")
    background-size 4rem
  &.s-css
    background-image url("https://upload.wikimedia.org/wikipedia/commons/3/3d/CSS.3.svg")
  &.s-js
    background-image url("https://seeklogo.com/images/N/nodejs-logo-FBE122E377-seeklogo.com.png")
svg.pro
  position absolute
  background-color transparent
  top 0
  right 0
  width 100%
  height 100%
  circle
    cx 50%
    cy 50%
    r 45%
    fill none
    stroke $prof_strong
    stroke-width 6
    stroke-dasharray 238
    stroke-dashoffset 238
    animation-name showProgress
    animation-duration 1s
    animation-iteration-count 1
    animation-timing-function linear
    animation-fill-mode forwards
    
@keyframes showProgress
  to
    stroke-dashoffset 40

</style>
