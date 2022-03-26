<template>
  <div>
    <div class="footer-basic">
      <footer>
        <div class="contact">
          <h3>Contact Me</h3>
        </div>
        <div class="social">
          <a href="https://www.facebook.com/arm53797/" target="_blank"><i class="icon ion-social-facebook"></i></a
          ><a href="https://twitter.com/TheEvilInMyMin1" target="_blank"><i class="icon ion-social-twitter"></i></a
          ><a href="https://github.com/state-dogs-001" target="_blank"><i class="icon ion-social-github"></i></a>
        </div>
        <p class="copyright">Anime API Test By Jaruwat Taengnuan</p>
      </footer>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.footer-basic {
  padding: 40px 0;
  background-color: #f0ad4e;
  color: #fff;
}

.footer-basic .contact {
  text-align: center;
  color: #fff;
}

.footer-basic ul {
  padding: 0;
  list-style: none;
  text-align: center;
  font-size: 18px;
  line-height: 1.6;
  margin-bottom: 0;
}

.footer-basic li {
  padding: 0 10px;
}

.footer-basic ul a {
  color: inherit;
  text-decoration: none;
  opacity: 0.8;
}

.footer-basic ul a:hover {
  opacity: 1;
}

.footer-basic .social {
  text-align: center;
  padding-bottom: 25px;
}

.footer-basic .social > a {
  font-size: 24px;
  width: 40px;
  height: 40px;
  line-height: 40px;
  display: inline-block;
  text-align: center;
  border-radius: 50%;
  border: 1px solid #fff;
  margin: 0 8px;
  color: inherit;
  opacity: 0.75;
}

.footer-basic .social > a:hover {
  opacity: 0.9;
}

.footer-basic .copyright {
  margin-top: 15px;
  text-align: center;
  font-size: 13px;
  color: #fff;
  margin-bottom: 0;
}
</style>