<template>
    <!-- ======= Header ======= -->
    <header id="header" class="fixed-top">
        <div class="container d-flex align-items-center">
          
            <nav class="nav-menu d-none d-lg-block">
                <ul>
                    <li class="active"><a href="/"><router-link to="/">Home</router-link></a></li>
                    <li><a href="/#about">About</a></li>
                    <li><a href="/#team">Team</a></li>
                    <li><a href="/#contact">Contact</a></li>
                    <li><a href="/docs">Forms</a></li>
                    <li class="drop-down"><a href="#">Profile</a>
                    <ul>
                        <li><a href="/login">Login</a></li>
                        <li><a href="/signup">Sign Up</a></li>
                    </ul>
                    </li>
                </ul>
            </nav><!-- .nav-menu -->
        </div>

        
    </header><!-- End Header -->

</template>

<script>
import axios from 'axios'
export default {
    name: 'head',
    methods: {
      postData: function(){
        axios({
          method: 'POST',
          url: 'http://localhost:3000/act/addCouncil',
          data: {
            name: 'something',
            chapterId: 1,
            category: 'College Red Cross Youth'
          }
        })
      }
    }
}
</script>

<style scoped>
    #header {
        background: #fff;
        transition: all 0.5s;
        z-index: 997;
        padding: 25px 0;
        top: 40px;
        box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.1);
    }

    #header.header-scrolled {
        top: 0;
        padding: 15px;
    }

    #header .logo {
        font-size: 32px;
        margin: 0;
        padding: 0;
        line-height: 1;
        font-weight: 600;
        letter-spacing: 0.8px;
        font-family: "Poppins", sans-serif;
    }

    #header .logo a {
        color: #222222;
    }

    #header .logo a span {
        color: #ea1010;
    }

    #header .logo img {
        max-height: 45px;
    }

    @media (max-width: 992px) {
        #header {
            padding: 15px;
            top: 0;
        }
        #header .logo {
            font-size: 28px;
        }
    }

/* ==============================================================================
                            All the CSS for the Navbar
=================================================================================*/
  .nav-menu ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  .nav-menu > ul {
    display: flex;
  }

  .nav-menu > ul > li {
    position: relative;
    white-space: nowrap;
    padding: 10px 0 10px 28px;
  }

  .nav-menu a {
    display: block;
    position: relative;
    color: #222222;
    transition: 0.3s;
    font-size: 15px;
    font-weight: 600;
    padding: 0 3px;
    font-family: "Open Sans", sans-serif;
  }

  .nav-menu > ul > li > a:before {
    content: "";
    position: absolute;
    width: 100%;
    height: 2px;
    bottom: -5px;
    left: 0;
    background-color: #ea1010;
    visibility: hidden;
    width: 0px;
    transition: all 0.3s ease-in-out 0s;
  }

  .nav-menu a:hover:before, .nav-menu li:hover > a:before, .nav-menu .active > a:before {
    visibility: visible;
    width: 100%;
  }

  .nav-menu a:hover, .nav-menu .active > a, .nav-menu li:hover > a {
    color: #ea1010;
  }

  .nav-menu .drop-down ul {
    display: block;
    position: absolute;
    left: 26px;
    top: calc(100% + 30px);
    z-index: 99;
    opacity: 0;
    visibility: hidden;
    padding: 10px 0;
    background: #fff;
    box-shadow: 0px 0px 30px rgba(127, 137, 161, 0.25);
    transition: 0.3s;
  }

  .nav-menu .drop-down:hover > ul {
    opacity: 1;
    top: 100%;
    visibility: visible;
  }

  .nav-menu .drop-down li {
    min-width: 180px;
    position: relative;
  }

  .nav-menu .drop-down ul a {
    padding: 10px 20px;
    font-size: 14px;
    font-weight: 500;
    text-transform: none;
    color: #062b5b;
  }

  .nav-menu .drop-down ul a:hover, .nav-menu .drop-down ul .active > a, .nav-menu .drop-down ul li:hover > a {
    color: #ea1010;
  }

  .nav-menu .drop-down > a:after {
    content: "\ea99";
    font-family: IcoFont;
    padding-left: 5px;
  }

  .nav-menu .drop-down .drop-down ul {
    top: 0;
    left: calc(100% - 30px);
  }

  .nav-menu .drop-down .drop-down:hover > ul {
    opacity: 1;
    top: 0;
    left: 100%;
  }

  .nav-menu .drop-down .drop-down > a {
    padding-right: 35px;
  }

  .nav-menu .drop-down .drop-down > a:after {
    content: "\eaa0";
    font-family: IcoFont;
    position: absolute;
    right: 15px;
  }

  @media (max-width: 1366px) {
    .nav-menu .drop-down .drop-down ul {
      left: -90%;
    }
    .nav-menu .drop-down .drop-down:hover > ul {
      left: -100%;
    }
    .nav-menu .drop-down .drop-down > a:after {
      content: "\ea9d";
    }
  }

  /* Mobile Navigation */
  .mobile-nav-toggle {
    position: fixed;
    right: 15px;
    top: 15px;
    z-index: 9998;
    border: 0;
    background: none;
    font-size: 24px;
    transition: all 0.4s;
    outline: none !important;
    line-height: 1;
    cursor: pointer;
    text-align: right;
  }

  .mobile-nav-toggle i {
    color: #222222;
  }

  .mobile-nav {
    position: fixed;
    top: 55px;
    right: 15px;
    bottom: 15px;
    left: 15px;
    z-index: 9999;
    overflow-y: auto;
    background: #fff;
    transition: ease-in-out 0.2s;
    opacity: 0;
    visibility: hidden;
    border-radius: 10px;
    padding: 10px 0;
  }

  .mobile-nav * {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  .mobile-nav a {
    display: block;
    position: relative;
    color: #222222;
    padding: 10px 20px;
    font-weight: 500;
    outline: none;
  }

  .mobile-nav a:hover, .mobile-nav .active > a, .mobile-nav li:hover > a {
    color: #ea1010;
    text-decoration: none;
  }

  .mobile-nav .drop-down > a:after {
    content: "\ea99";
    font-family: IcoFont;
    padding-left: 10px;
    position: absolute;
    right: 15px;
  }

  .mobile-nav .active.drop-down > a:after {
    content: "\eaa1";
  }

  .mobile-nav .drop-down > a {
    padding-right: 35px;
  }

  .mobile-nav .drop-down ul {
    display: none;
    overflow: hidden;
  }

  .mobile-nav .drop-down li {
    padding-left: 20px;
  }

  .mobile-nav-overly {
    width: 100%;
    height: 100%;
    z-index: 9997;
    top: 0;
    left: 0;
    position: fixed;
    background: rgba(9, 9, 9, 0.6);
    overflow: hidden;
    display: none;
    transition: ease-in-out 0.2s;
  }

  .mobile-nav-active {
    overflow: hidden;
  }

  .mobile-nav-active .mobile-nav {
    opacity: 1;
    visibility: visible;
  }

  .mobile-nav-active .mobile-nav-toggle i {
    color: #fff;
  }
</style>