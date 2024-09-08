<template>
        <aside class="sidebar" data-sidebar>

            <div class="sidebar-info">
              <figure class="avatar-box">
                <img src="~/assets/images/profile.png" alt="Bilal Shafiq" width="80">
              </figure>
              <div class="info-content">
                <h1 class="name" title="Bilal Shafiq">Bilal Shafiq</h1>
                <p class="title">Web Developer</p>
              </div>
          
              <button class="info_more-btn" data-sidebar-btn>
                <span>Show Contacts</span>
          
                <ion-icon name="chevron-down"></ion-icon>
              </button>
          
            </div>
          
            <div class="sidebar-info_more">
          
              <div class="separator"></div>
          
              <ul class="contacts-list">
          
                <li class="contact-item">
          
                  <div class="icon-box">
                    <ion-icon name="mail-outline"></ion-icon>
                  </div>
          
                  <div class="contact-info">
                    <p class="contact-title">Email</p>
          
                    <a href="mailto:mbilalshafiq9@gmail.com" class="contact-link">mbilalshafiq9@gmail.com</a>
                  </div>
          
                </li>
          
                <li class="contact-item">
          
                  <div class="icon-box">
                    <ion-icon name="phone-portrait-outline"></ion-icon>
                  </div>
          
                  <div class="contact-info">
                    <p class="contact-title">Phone</p>
          
                    <a href="tel:+923434692063" class="contact-link">+92 3434692063</a>
                  </div>
          
                </li>
          
                <li class="contact-item">
          
                  <div class="icon-box">
                    <ion-icon name="language-outline"></ion-icon>
                  </div>
          
                  <div class="contact-info">
                    <p class="contact-title">Languages</p>
          
                    <time datetime="1982-06-23">English - Conversational</time>
                    <time datetime="1982-06-23">Urdu - Native</time>
                  </div>
          
                </li>
          
                <li class="contact-item">
          
                  <div class="icon-box">
                    <ion-icon name="location-outline"></ion-icon>
                  </div>
          
                  <div class="contact-info">
                    <p class="contact-title">Location</p>
          
                    <address>Lalazar Colony, Sahiwal</address>
                  </div>
          
                </li>
          
              </ul>
          
              <div class="separator"></div>
          
              <ul class="social-list">
          
                <li class="social-item">
                  <a href="https://www.linkedin.com/in/bilal-shafique-28b1b2192/" target="_blank"  class="social-link">
                    <ion-icon name="logo-linkedin"></ion-icon>
                  </a>
                </li>
          
                <li class="social-item">
                  <a href="https://github.com/mbilalshafiq9/" target="_blank" class="social-link">
                    <ion-icon name="logo-github"></ion-icon>
                  </a>
                </li>
          
                <li class="social-item">
                  <a href="#" class="social-link">
                    <ion-icon name="logo-stackoverflow"></ion-icon>
                  </a>
                </li>
          
              </ul>
          
            </div>
          
        </aside>
</template>