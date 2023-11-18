
<template>
    <!-- style="background-image: url(assets/img/overlay-bg.jpg)" -->
    <section id="contact" class="paralax-mf footer-paralax bg-image sect-mt4 route" >
      <!-- <div class="overlay-mf"></div> -->
      <div class="container">
        <div class="row">
          <div class="col-sm-12">
            <div class="contact-mf">
              <div id="contact" class="box-shadow-full">
                <div class="row">
                  <div class="col-md-6">
                    <div class="title-box-2">
                      <h5 class="title-left">
                        Message Me
                      </h5>
                    </div>
                    <div>
                      <form @submit.prevent="submit" class="php-email-form">
                        <div class="row">
                          <div class="col-md-12 mb-3">
                            <div class="form-group">
                              <input type="text" v-model="form.name" class="form-control" id="name" placeholder="Your Name" required>
                            </div>
                          </div>
                          <div class="col-md-12 mb-3">
                            <div class="form-group">
                              <input type="email" v-model="form.email" class="form-control" name="email" id="email" placeholder="Your Email" required>
                            </div>
                          </div>
                          <!-- {/* <div class="col-md-12 mb-3">
                            <div class="form-group">
                              <input type="text" class="form-control" name="subject" id="subject" placeholder="Subject" required>
                            </div>
                          </div> */} -->
                          <div class="col-md-12">
                            <div class="form-group">
                              <textarea class="form-control" v-model="form.message" name="message" rows="5" placeholder="Message" required></textarea>
                            </div>
                          </div>
                          <!-- {/* <div class="col-md-12 text-center my-3">
                            <div class="loading">Loading</div>
                            <div class="error-message"></div>
                            <div class="sent-message">Your message has been sent. Thank you!</div>
                          </div> */} -->
                          <div class="col-md-12 text-center">
                            <button type="submit" :disabled="isLoading" class="button button-a button-big button-rouded">
                              {{loadingStatus ? "Submitting...":"Send Message"}} </button>
                          </div>
                        </div>
                      </form>
                    </div>
                  </div>
                  <div class="col-md-6">
                    <div class="title-box-2 pt-4 pt-md-0">
                      <h5 class="title-left">
                        Get in Touch
                      </h5>
                    </div>
                    <div class="more-info">
                      <p class="lead">
                        If you have any questions or any business that you would like me to handle, please do not hesitate to get in touch
                      </p>
                      <ul class="list-ico">
                        <li><span class="bi bi-geo-alt"></span> 1205 Sadelmakerebyn 9b, Bunkeflostrand, Malmo, 212 58</li>
                        <li><span class="bi bi-phone"></span> (+46) 793559952</li>
                        <li><span class="bi bi-envelope"></span> jerrydaniels201@gmail.com</li>
                      </ul>
                    </div>
                    <div class="socials">
                      <ul>
                        <li>
                          <a href="">
                            <!-- <span class="ico-circle"> -->
                              <i class="bi bi-facebook"></i>
                            <!-- </span> -->
                          </a>
                        </li>
                        <li>
                          <a href="" style="margin: 1rem">
                            <!-- <span class="ico-circle"> -->
                              <i class="bi bi-instagram"></i>
                            <!-- </span> -->
                          </a>
                        </li>
                        <li>
                          <a href="" >
                            <!-- <span class="ico-circle"> -->
                              <i class="bi bi-twitter"></i>
                            <!-- </span> -->
                          </a>
                        </li>
                        <li>
                          <a href="" style="margin: 1rem">
                            <!-- <span class="ico-circle"> -->
                              <i class="bi bi-linkedin"></i>
                            <!-- </span> -->
                          </a>
                        </li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
</template>

<script>
export default {
  data() {
    return {
      form: {
          name: '',
        email: '',
        message: ''
      },
      response:{
        msg: "",
        isError: false
      },
      isLoading: false
    }
  },
  computed:{
    loadingStatus() {
      return this.isLoading;
    },
    clearForm() {
      this.form.name = ""
      this.form.email = ""
      this.form.message = ""
    }
  },
  methods: {
    startLoading() {
      this.isLoading = true;
    },
    stopLoading() {
      this.isLoading = false;
    },
    async submit() {
      this.startLoading()
      let body = {
        name: this.form.name,
          email: this.form.email,
          message: this.form.message,
      }
    return fetch(
      import.meta.env.VITE_BASE_URL,
      {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body:JSON.stringify(body),
      }
    )
      .then((data) => data.json())
      .then((res) => {
        const {msg, isError} = res
        alert(msg)   
        this.stopLoading()   
        this.clearForm()  
      });
    }
  }
}
</script>
