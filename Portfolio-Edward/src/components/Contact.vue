<template>
    <div class="contact" id="contact">
      <div class="container">
        <h5>Get In Touch</h5>
        <h2>Contact Me</h2>
      </div>
      <div class="container contact__container">
        <div class="contact__options">
          <div class="contact__option">
            <i class="bi bi-envelope-fill contact__option-icon"></i>
            <h4>Email</h4>
            <h5>edward.habermann@icloud.com</h5>
            <a
              href="mailto:edward.habermann@icloud.com"
              target="_blank"
              rel="noopener noreferrer"
            >
              Send a message
            </a>
          </div>
          <div class="contact__option">
            <i class="bi bi-chat-dots-fill contact__option-icon"></i>
            <h4>Messenger</h4>
            <h5>Edward Habermann</h5>
            <a
              href="https://m.me/edward.achiever"
              target="_blank"
              rel="noopener noreferrer"
            >
              Send a message
            </a>
          </div>
          <div class="contact__option">
            <i class="bi bi-whatsapp contact__option-icon"></i>
            <h4>WhatsApp</h4>
            <h5>+49 176 34992789</h5>
            <a
              href="https://api.whatsapp.com/send?=+4917634992789"
              target="_blank"
              rel="noopener noreferrer"
            >
              Send a message
            </a>
          </div>
        </div>
        <!-- END OF CONTACT OPTION -->
        <form ref="form" @submit.prevent="sendEmail">
          <input type="text" name="name" placeholder="Your Full Name" required />
          <input type="email" name="email" placeholder="Your Email" />
          <textarea name="message" rows="7" placeholder="Your Message"></textarea>
          <button type="submit" class="btn">
            Send Message
          </button>
        </form>
      </div>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import emailjs from '@emailjs/browser';
  
  export default defineComponent({
    name: 'Contact',
    methods: {
  sendEmail() {
    const form = this.$refs.form as HTMLFormElement;
    if (form instanceof HTMLFormElement) {
      emailjs.sendForm('service_9rnlsog', 'template_83jphqy', form, 'hmav0ryQrwpFGgSbJ')
        .then((result: any) => {
          console.log('SUCCESS!', result.text);
        }, (error: any) => {
          console.log('FAILED...', error.text);
        });
    }
  }
}
  });
  </script>

<style>
#contact {
    margin-top: 5rem;
}


.container.contact__container {
    width: 80%;
    display: grid;
    grid-template-columns: 30% 58%;
    gap: 12%;
}

.contact__options {
    display: flex;
    flex-direction: column;
    gap: 1.2rem;
}

.contact__option {
    background: var(--color-bg-variant);
    padding: 1.2rem;
    border-radius: 1.2rem;
    text-align: center;
    border: 1px solid transparent;
    transition: var(--transition);
}

.contact__option:hover {
    background: transparent;
    border-color: var(--color-primary-variant);
}

.contact__option-icon {
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
}

.contact__option a {
    margin-top: 0.7rem;
    display: inline-block;
    font-size: 0.8rem;
}

/* FORM */

form {
    display: flex;
    flex-direction: column;
    gap: 1.2rem;
}

input,
textarea {
    width: 100%;
    padding: 1.5rem;
    border-radius: 0.5rem;
    background: transparent;
    border: 2px solid var(--color-primary-variant);
    resize: none;
    color: var(--color-white);
}

/* MEDIA QUERIES (MEDIUM DEVICES) */

@media screen and (max-width: 1024px) {
    .container.contact__container {
        width: 80%;
        grid-template-columns: 1fr;
        gap: 2rem;
    }
}


/* MEDIA QUERIES (SMALL DEVICES) */

@media screen and (max-width: 600px) {
    .container.contact__container {
        width: var(--container-width-sm);
    }
}
</style>
  
  