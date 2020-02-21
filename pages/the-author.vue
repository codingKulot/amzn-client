<template>
<body class="body-class" data-spy="scroll" data-target="#navbarResponsive">
  <!-- Start Home Section -->
  <div id="home">
    <!-- Navigation -->
    <nav class="navbar navbar-expand-md navbar-dark bg-dark fixed-top">
      <a class="navbar-brand" href="/the-author"><img src="/img/coding.png"></a>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarResponsive">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarResponsive">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <a href="#home" class="nav-link">Home</a>
          </li>
          <li class="nav-item">
            <a href="#technologies" class="nav-link">Technologies</a>
          </li>
          <li class="nav-item">
            <a href="#interest" class="nav-link">Interests</a>
          </li>
          <li class="nav-item">
            <a href="#contact" class="nav-link">Contact</a>
          </li>
        </ul>
      </div>
    </nav>
    <!-- Start Image Slider -->
    <div class="carousel slide" id="carouselExampleIndicators" data-ride="carousel" data-interval="3500">
      <ol class="carousel-indicators">
        <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
        <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
        <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
      </ol>
      <div class="carousel-inner" role="listbox">
        <!-- Slide 1 -->
        <div class="carousel-item active" style="background-image: url(/img/image-one.jpg); background-size: 100% 100%;">
          <div class="carousel-caption text-center">
            <h1>Welcome to my Portfolio</h1>
            <h3>Full Stack Web Developer</h3>
          </div>
        </div>
        <!-- Slide 2 -->
        <div class="carousel-item" style="background-image: url(/img/image-two.jpg); background-size: 100% 100%;"></div>
        <!-- Slide 3 -->
        <div class="carousel-item" style="background-image: url(/img/image-three.jpg); background-size: 100% 100%;"></div>
        <!-- Prev & Next Buttons -->
        <a href="#carouselExampleIndicators" class="carousel-control-prev" role="button" data-slide="prev">
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        </a>
        <a href="#carouselExampleIndicators" class="carousel-control-next" role="button" data-slide="next">
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
        </a>
      </div>
    </div>
    <!-- End Image Slider -->
    <div id="course" class="offset">

    <!-- Start The Author Section -->

    <!-- <div class="col-12 narrow text-center">
	    <h1>Nuno Theme Advanced Bootstrap Course</h1>
	    <p class="lead">Learn Bootstrap by creating an advanced Bootstrap 4 Responsive Website Template from scratch, with no steps skipped!</p>
	    <a class="btn btn-secondary btn-md" href="https:" target="_blank">W3NEWBIE COURSES</a>
    </div> -->

    <div class="col-12 text-center">
      <h3 class="heading">About Me</h3>
      <div class="heading-underline"></div>
    </div>

    <div class="row">
      <div class="col-md-3"></div>
      <div class="col-md-6 author" style="margin-top: -25px; margin-bottom: 25px">
        <div class="row">
          <div class="col-md-4">
            <img src="/img/admin.jpg">
          </div>
          <div class="col-md-8">
            <blockquote>
              <i class="fas fa-quote-left"></i>
              Motivated and eager to escalate my competence in a growth-oriented organization as a Web Developer. To learn and heighten continuously in the field of Web Technology.
              <i class="fas fa-quote-right"></i>
              <hr class="author-hr">
              <cite>&#8212; Ronilo Jr., Full Stack Web Developer</cite>
            </blockquote>
          </div>
        </div>
      </div>
      <div class="col-md-3"></div>
    </div>



    <!-- End The Author Section -->

    </div>
  
  <!-- End Home Section -->

  <!-- Start Technologies Section -->
    <div id="technologies" class="offset">

      <div class="jumbotron container-fluid">
        <div class="col-12 text-center">
          <h3 class="heading">Technologies</h3>
          <div class="heading-underline"></div>
        </div>
        <div class="row no-padding">

          <div class="col-sm-3">
            <div class="technologies">
              <a href="/img/tech/angular.png" target="_blank">
                <img src="/img/tech/angular.png">
              </a>
            </div>
          </div>
          <div class="col-sm-3">
            <div class="technologies">
              <a href="/img/tech/vue.png" target="_blank">
                <img src="/img/tech/vue.png">
              </a>
            </div>
          </div>
          <div class="col-sm-3">
            <div class="technologies">
              <a href="/img/tech/bootstrap.png" target="_blank">
                <img src="/img/tech/bootstrap.png">
              </a>
            </div>
          </div>
          <div class="col-sm-3">
            <div class="technologies">
              <a href="/img/tech/node.png" target="_blank">
                <img src="/img/tech/node.png">
              </a>
            </div>
          </div>
          <div class="col-sm-3">
            <div class="technologies">
              <a href="/img/tech/mongodb.jpg" target="_blank">
                <img src="/img/tech/mongodb.jpg">
              </a>
            </div>
          </div>
          <div class="col-sm-3">
            <div class="technologies">
              <a href="/img/tech/aws.png" target="_blank">
                <img src="/img/tech/aws.png">
              </a>
            </div>
          </div>
          <div class="col-sm-3">
            <div class="technologies">
              <a href="/img/tech/firebase.jpeg" target="_blank">
                <img src="/img/tech/firebase.jpeg">
              </a>
            </div>
          </div>
          <div class="col-sm-3">
            <div class="technologies">
              <a href="/img/tech/git.jpg" target="_blank">
                <img src="/img/tech/git.jpg">
              </a>
            </div>
          </div>

          <div class="narrow text-center">
            <div class="col-12">
              <p></p>
              <a href="/" class="btn btn-secondary btn-md">Example Project - Amazon clone</a>
            </div>
          </div>

        </div>
      </div>

    </div>
  <!-- End Technologies Section -->

  <!-- Start Interests Section -->
    <div id="interest" class="offset">
      <div class="col-12 text-center">
        <h3 class="heading">Interests</h3>
        <div class="heading-underline"></div>
      </div>
      <div class="row">
        <div class="col-md-2"></div>
      <div class="col-md-8">
              <div class="row padding">

        <div class="col-md-4">
          <div class="card text-center">
            <img src="/img/interest-one.jpg" class="card-img-top">
            <div class="card-body">
              <h3>Web Development</h3>
              <h6>"After all it is the internet advertising billboard for you and your company".</h6>
            </div>
          </div>
        </div>

        <div class="col-md-4">
          <div class="card text-center">
            <img src="/img/interest-two.jpg" class="card-img-top">
            <div class="card-body">
              <h3>Travelling</h3>
              <h6>“Like all great travellers, I have seen more than I remember and remember more than I have seen.”</h6>
            </div>
          </div>
        </div>

        <div class="col-md-4">
          <div class="card text-center">
            <img src="/img/interest-three.jpg" class="card-img-top">
            <div class="card-body">
              <h3>Photography</h3>
              <h6>“A photographer is aware of the tiny moments in a persons life that reveal greater truths”</h6>
            </div>
          </div>
        </div>

      </div>
      </div>
      <div class="col-md-2"></div>
      </div>

    </div>
  <!-- End Interests Section -->

  <!-- Start Contact Section -->
    <div id="contact" class="offset">
      <footer>
        <div class="row justify-content-center">
          <div class="col-md-5 text-center">
            <img src="/img/coding.png" alt="">
            <p>The main goal is to exceed the expectations in terms of designs, functionalities that represents everything your business needs to compete in the modern marketplace.</p>
            <strong>Contact Info :</strong>
            <p>(639) 2642 85823<br>ronilojunior07@gmail.com</p>
            <a href="https://www.gmail.com" target="_blank"><i class="fab fa-google"></i></a>
            <a href="https://www.linkedin.com" target="_blank"><i class="fab fa-linkedin"></i></a>
            <a href="https://www.facebook.com" target="_blank"><i class="fab fa-facebook-square"></i></a>
          </div>
          <hr class="socket">
          &copy; Coding.
        </div>
      </footer>
    </div>
  <!-- End Contact Section -->
  </div>
</body>

</template>
<script>
export default {
    layout: 'none',
    head () {
      return {
        script: [
          { src: "https://code.jquery.com/jquery-3.4.1.min.js", integrity: "sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo=", crossorigin:"anonymous" },
          { src: "https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js", integrity:"sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6", crossorigin:"anonymous" },
          { src: "https://use.fontawesome.com/releases/v5.6.1/js/all.js" }
        ],
        link: [
          {
            rel: "stylesheet", href:"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css", integrity: "sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T", crossorigin:"anonymous"
          }
        ]
      }
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Lato:400,700&display=swap');

.body-class {
  overflow-x: hidden;
  font-family: 'Lato', sans-serif;
  color: #505962;
}

.offset:before {
  height: 3rem;
  margin-top: -.1rem;
  content: "";
  display: block;
}

/* Navbar */

.navbar {
  text-transform: uppercase;
  font-weight: 700;
  font-size: .9rem;
  letter-spacing:.1rem;
  height: 3rem;
  /* background: rgba(0, 0, 0, .1)!important; */
}

.navbar-brand img {
  height: 2rem;
  width: 7rem;
}

.navbar-nav li {
  padding-right: .7rem;
}

.navbar-dark .navbar-nav .nav-link {
  color: white;
  padding-top: .8rem;
}

.navbar-dark .navbar-nav .nav-link.active,
.navbar-dark .navbar-nav .nav-link:hover {
  color:#3bc45f;
}

/* Slider */
.carousel-item {
  height: 100vh;
}

.carousel-caption {
  position: absolute;
  top: 38%;
  text-transform: uppercase;
  width: 100%;
  right: 0;
  left: 0;
}

.carousel-caption h1 {
  font-size: 3.8rem;
  font-weight: 700;
  letter-spacing: .3rem;
  text-shadow: .1rem .1rem .8rem black;
  padding-bottom: 1rem;
}

carousel-caption h3 {
   font-size: 2rem;
   text-shadow: .1rem .1rem .5rem black;
   padding-bottom: 1.6rem;
}

/* Author */
.author img {
  width: 100%;
  border: 2.1px solid #666b71;
  border-radius: 50%;
}

blockquote {
  margin: 1rem;
  font-size: 1rem;
}

blockquote path {
  color: #3bc45f
}

.author-hr {
  border-top: .1rem solid #666b71;
}

  /*============= COURSE SECTION =============*/
.narrow {
  width: 75%;
  margin: 0 auto;
  padding-top: 2rem;
}
.narrow h1 {
    font-size: 2.4rem;
  }

.jumbotron {
  border-radius: 0;
  padding: 2rem 0 2rem;
  margin-bottom: 0;
}

h3.heading {
  font-size: 1.9rem;
  font-weight: 700;
  text-transform: uppercase;
  padding-top: 1.9rem;
  padding-bottom: 1.9rem;
}

.heading-underline {
  width: 3rem;
  height:  .2rem;
  background-color: #3bc45f;
  margin: 0 auto 2rem;
}

/* Technologies */
.technologies img {
  max-width: 100%;
  transition: transform .5s ease;
}

.technologies img:hover {
  transform: scale(1.2);
  cursor: zoom-in;
}

.technologies {
  overflow: hidden;
}

.row.no-padding [class*=col-] {
  padding: 0;
}

/* Contact */
footer {
  background-color: #40474e;
  color: white;
  padding: 2rem 0 3rem;
  margin-top: 1rem;
}

footer img {
  height: 7rem;
  margin: 1.5rem 0;
}

footer a {
  color: white;
}

footer svg.svg-inline--fa {
  font-size: 1.6rem;
  margin: 1.2rem .5rem 0 0;
}

footer svg.svg-inline--fa:hover {
  color: #3bc45f;
}

hr.socket {
  border-top: .2rem solid #666b71;
  width: 100%;
}

.btn-secondary {
  border-width: medium;
  border-radius: 0;
  padding: .6rem 1.2rem;
  font-size: 1.2rem;
  text-transform: uppercase;
  margin: 1rem;
  border-color: #3bc45f;
  background-color: #3bc45f;
  color: white;
}

.btn-secondary:hover,
.btn-secondary:focus {
  border-color: #3bc45f;
  background-color: #3bc45f;
  color: white;
}


/*============ BOOTSTRAP BREAK POINTS:

Extra small (xs) devices (portrait phones, less than 576px)
No media query since this is the default in Bootstrap

Small (sm) devices (landscape phones, 576px and up)
@media (min-width: 576px) { ... }

Medium (md) devices (tablets, 768px and up)
@media (min-width: 768px) { ... }

Large (lg) devices (desktops, 992px and up)
@media (min-width: 992px) { ... }

Extra (xl) large devices (large desktops, 1200px and up)
@media (min-width: 1200px) { ... }

=============*/

/*--- Extra Bootstrap Column Padding --*/
[class*="col-"] {
  padding: 1rem;
}

/*--- Bootstrap Mobile Gutter Fix --*/
.row, .container-fluid {
margin-left: 0px!important;
margin-right: 0px!important;
}

/*--- Fix for Fixed Navbar jumping on scroll --*/
/* .fixed-top  {
 -webkit-backface-visibility: hidden;
} */

/*--- Fixed Landing Page Section --*/
.landing {
  position: relative;
  width: 100%;
  height: 100vh;
  display: table;
  z-index: -1;
}
.home-wrap {
  clip: rect(0, auto, auto, 0);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
.home-inner {
  position: fixed;
  display: table;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center center;
  -webkit-transform: translateZ(0);
          transform: translateZ(0);
  will-change: transform;
}

/*--- iOS Fixed Background Image --*/
.fixed-background {
  position: relative;
  width: 100%;
}
.fixed-wrap {
  clip: rect(0, auto, auto, 0);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -999!important;
}
.fixed {
  position: fixed;
  display: block;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center center;
  -webkit-transform: translateZ(0);
          transform: translateZ(0);
  will-change: transform;
}
</style>