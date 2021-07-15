<template>
 <transition appear name = "fade">
  <div class="row m-5">
      <div class="col-sm-7">
        <p class="about text-start">
            Inspired in the works of H.R. Giger, 
            White Wolf's <cite>World of Darkness</cite> and David Cronenberg films.
            Her main themes are dark mutations, transformations and twisted creatures. 
          <br>
          <br>  
            Daniela Kazarian lives with her two cats, dog and parrot in Buenos Aires,
            Argentina. She is a web developer and artist,
            and in her free time she loves playing video and tabletop games.
        </p>        
      </div>
      <div class="col-sm-5">
      <figure class="image d-flex flex-column align-items-center">
          <img class="img-fluid" src="../assets/images/Incarna.jpg" alt="Daniela Kazarian fictonalized persona, alien-like creature" />
        <blockquote class="text-start">
          <p>
            <i>
              <strong>"Some people say my work is often depressing and pessimistic,
              with the emphasis on death, blood, overcrowding, 
              strange beings and so on, but I don't really think it is."</strong>
            </i>  
          </p>
        </blockquote>
        <figcaption>
          <p>
            &mdash; H.R. Giger
          </p>
        </figcaption>
      </figure>
    </div>
    </div>
  </transition>
</template>

<style scoped lang="scss">

  $small-mobile-width: 320px;
  $mobile-width: 600px;
  $tablet-width: 900px;
  $desktop-width: 1200px;
  $large-desktop-width: 1800px;

  @mixin s-mobile {
      @media (max-width: #{$small-mobile-width}) {
        @content;
      }
    }
  @mixin mobile {
    @media (min-width: #{$small-mobile-width + 1px}) and (max-width: #{$mobile-width}) {
      @content;
    }
  }
  @mixin s-tablet {
      @media (min-width: #{$mobile-width + 1px}) and (max-width: #{$tablet-width}) {
      @content;
    }
  }
  @mixin l-tablet {
      @media (min-width: #{$tablet-width + 1px}) and (max-width: #{$desktop-width}) {
      @content;
    }
  }
  @mixin desktop {
      @media (min-width: #{$desktop-width + 1px}) and (max-width: #{$large-desktop-width}) {
      @content;
    }
  }
  @mixin l-desktop {
      @media (min-width: #{$large-desktop-width + 1px}){
      @content;
    }
  }
  p {
    font-size: 2.5rem;
    font-family: 'Stylish', sans-serif;
     @include mobile{
      font-size:2rem
    }
  }
  .about {
    margin-left:150px;
    margin-top:100px;
      @include mobile {
        margin-left:0px;
        margin-top:0px
      }
      @include s-mobile {
      margin-left:0px;
      margin-top:0px
      }
      @include s-tablet {
      margin-left:0px;
      margin-top:0px
      }
      @include l-tablet {
      margin-left:0px;
      margin-top:0px
      }
  }
  img {
    width:60%;
      @include mobile {
        width:90%;
        margin-top:3rem;
      }
      @include s-mobile {
        width:90%;
        margin-top:3rem;
      }
      @include s-tablet {
        width:50%;
      }
  }
  blockquote {
    width:60%;
    @include mobile {
        width:90%;
      }
    @include s-mobile {
        width:90%;
      }
    p {
      font-size: 2rem
    }
  }
  .fade-enter-from {
    opacity: 0;
  }
  .fade-enter-to {
    opacity:1
  }
  .fade-enter-active {
    transition: all 2s ease
  }
</style>

