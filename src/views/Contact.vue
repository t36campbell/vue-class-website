<template>
  <div class="site-section">
    <b-container fluid>
      <div class="row mb-5">
        <div class="col-12">
          <h3 class="section-sub-title text-center">Contact Form</h3>
          <h2 class="section-title text-center mb-3">Schedule an Appointment</h2>
          <b-form @submit="onSubmit" class="col-12">
            <div class="row">
              <div class="col-md-6 col-sm-12">
                <div class="row form-group">
                  <b-form-group
                    id="input-group-1"
                    class="col-md-12 text-black"
                    label="Select a Date:"
                    label-for="datepicker"
                  >
                    <b-form-datepicker
                      id="datepicker"
                      class="mb-2 form-control rounded-0"
                      v-model="$v.form.date.$model"
                      :state="validateState('date')"
                    ></b-form-datepicker>
                    <b-form-invalid-feedback>This is a required field.</b-form-invalid-feedback>
                  </b-form-group>
                </div>
              </div>
              <div class="col-md-6 col-sm-12">
                <div class="row form-group">
                  <b-form-group
                    id="input-group-2"
                    class="col-md-12 text-black"
                    label="Select a Time"
                    label-for="timepicker"
                  >
                    <b-form-timepicker
                      id="timepicker"
                      class="mb-2 form-control rounded-0"
                      locale="en-US"
                      v-model="$v.form.time.$model"
                      :state="validateState('time')"
                    ></b-form-timepicker>
                    <b-form-invalid-feedback>This is a required field.</b-form-invalid-feedback>
                  </b-form-group>
                </div>
              </div>
            </div>
            <hr />
            <div class="row">
              <div class="col-md-6 col-sm-12">
                <div class="row form-group">
                  <b-form-group
                    id="input-group-3"
                    class="col-md-12 text-black"
                    label="First Name:"
                    label-for="fname"
                  >
                    <b-form-input
                      id="fname"
                      class="col-md-12 form-control rounded-0"
                      v-model="$v.form.fname.$model"
                      :state="validateState('fname')"
                      placeholder="Enter Your First Name"
                    ></b-form-input>
                    <b-form-invalid-feedback>This is a required field.</b-form-invalid-feedback>
                  </b-form-group>
                </div>
              </div>
              <div class="col-md-6 col-sm-12">
                <div class="row form-group">
                  <b-form-group
                    id="input-group-4"
                    class="col-md-12 text-black"
                    label="Last Name:"
                    label-for="lname"
                  >
                    <b-form-input
                      id="lname"
                      class="col-md-12 form-control rounded-0"
                      v-model="$v.form.lname.$model"
                      :state="validateState('lname')"
                      placeholder="Enter Your Last Name"
                    ></b-form-input>
                    <b-form-invalid-feedback>This is a required field.</b-form-invalid-feedback>
                  </b-form-group>
                </div>
              </div>
              <div class="col-md-6 col-sm-12">
                <div class="row form-group">
                  <b-form-group
                    id="input-group-5"
                    class="col-md-12 text-black"
                    label="Phone:"
                    label-for="phone"
                  >
                    <b-form-input
                      id="phone"
                      class="col-md-12 form-control rounded-0"
                      v-model="$v.form.phone.$model"
                      :state="validateState('phone')"
                      placeholder="Enter Your Phone Number"
                    ></b-form-input>
                    <b-form-invalid-feedback>This is a required field.</b-form-invalid-feedback>
                  </b-form-group>
                </div>
              </div>
              <div class="col-md-6 col-sm-12">
                <div class="row form-group">
                  <b-form-group
                    id="input-group-6"
                    class="col-md-12 text-black"
                    label="Email:"
                    label-for="email"
                  >
                    <b-form-input
                      id="email"
                      class="col-md-12 form-control rounded-0"
                      v-model="$v.form.email.$model"
                      type="email"
                      :state="validateState('email')"
                      placeholder="Enter Your Email"
                    ></b-form-input>
                    <b-form-invalid-feedback>This is a required field.</b-form-invalid-feedback>
                  </b-form-group>
                </div>
              </div>
            </div>
            <hr />
            <div class="row">
              <div class="col-md-6 col-sm-12">
                <div class="row form-group">
                  <b-form-group
                    id="input-group-7"
                    class="col-md-12 text-black"
                    label="Device Manufacturer:"
                    label-for="device-man"
                  >
                    <b-form-input
                      id="device-man"
                      class="col-md-12 form-control rounded-0"
                      v-model="$v.form.device_man.$model"
                      :state="validateState('device_man')"
                      placeholder="Enter the Name of Your Device"
                    ></b-form-input>
                    <b-form-invalid-feedback>This is a required field.</b-form-invalid-feedback>
                  </b-form-group>
                  <b-form-group
                    id="input-group-8"
                    class="col-md-12 text-black"
                    label="Device Model:"
                    label-for="device-mod"
                  >
                    <b-form-input
                      id="device-mod"
                      class="col-md-12 form-control rounded-0"
                      v-model="$v.form.device_mod.$model"
                      :state="validateState('device_mod')"
                      placeholder="Enter the Name of Your Device"
                    ></b-form-input>
                    <b-form-invalid-feedback>This is a required field.</b-form-invalid-feedback>
                  </b-form-group>
                </div>
              </div>
              <div class="col-md-6 col-sm-12">
                <div class="row form-group">
                  <b-form-group
                    id="input-group-9"
                    class="col-md-12 text-black"
                    label="Select a Service"
                    label-for="input-group-6"
                  >
                    <b-form-radio-group
                      id="radio-group-1"
                      v-model="$v.form.service.$model"
                      :options="options"
                      :state="validateState('service')"
                      stacked
                    ></b-form-radio-group>
                    <b-form-invalid-feedback>This is a required field.</b-form-invalid-feedback>
                  </b-form-group>
                </div>
              </div>
              <div class="col-md-12 text-center">
                <div class="mx-auto row form-group justify-content-center">
                  <b-button
                    class="col-md-3 btn btn-black btn-black mx-1 rounded-0"
                    @click="saveContact"
                  >Save for Later</b-button>
                  <br />
                  <b-button
                    class="col-md-3 btn btn-black btn-black mx-1 rounded-0"
                    type="submit"
                  >Submit</b-button>
                </div>
              </div>
            </div>
          </b-form>
        </div>
      </div>
    </b-container>
  </div>
</template>

<script>
import { validationMixin } from 'vuelidate';
import { required, email } from 'vuelidate/lib/validators';

export default {
  name: 'schedule',
  mixins: [validationMixin],
  data() {
    return {
      form: {
        date: null,
        time: null,
        fname: null,
        lname: null,
        phone: null,
        email: null,
        device_man: null,
        device_mod: null,
        service: null,
      },
      options: [
        { text: 'Mobile Phone Repair', value: 'mobile' },
        { text: 'Tablet Repair', value: 'tablet' },
        { text: 'Laptop Repair', value: 'laptop' },
        { text: 'Computer Repair', value: 'pc' },
        { text: 'Custom PC Builds', value: 'pc-build' },
        { text: 'Server Builds & Installs', value: 'server' },
      ],
    };
  },
  mounted() {
    if (localStorage.date) this.form.date = localStorage.date;
    if (localStorage.time) this.form.time = localStorage.time;
    if (localStorage.fname) this.form.fname = localStorage.fname;
    if (localStorage.lname) this.form.lname = localStorage.lname;
    if (localStorage.phone) this.form.phone = localStorage.phone;
    if (localStorage.email) this.form.email = localStorage.email;
    if (localStorage.device_man) this.form.device_man = localStorage.device_man;
    if (localStorage.device_mod) this.form.device_mod = localStorage.device_mod;
    if (localStorage.service) this.form.service = localStorage.service;
  },
  validations: {
    form: {
      date: {
        required,
      },
      time: {
        required,
      },
      fname: {
        required,
      },
      lname: {
        required,
      },
      phone: {
        required,
      },
      email: {
        required,
        email,
      },
      device_man: {
        required,
      },
      device_mod: {
        required,
      },
      service: {
        required,
      },
    },
  },
  methods: {
    validateState(name) {
      const { $dirty, $error } = this.$v.form[name];
      return $dirty ? !$error : null;
    },
    onSubmit(evt) {
      evt.preventDefault();
      this.$v.form.$touch();
      if (this.$v.form.$anyError) {
        return;
      }
      // eslint-disable-next-line no-alert
      alert(`Form submitted!\n${JSON.stringify(this.form)}`);
    },
    saveContact() {
      if (this.form.date) localStorage.date = this.form.date;
      if (this.form.time) localStorage.time = this.form.time;
      if (this.form.fname) localStorage.fname = this.form.fname;
      if (this.form.lname) localStorage.lname = this.form.lname;
      if (this.form.phone) localStorage.phone = this.form.phone;
      if (this.form.email) localStorage.email = this.form.email;
      if (this.form.device_man) localStorage.device_man = this.form.device_man;
      if (this.form.devide_mod) localStorage.device_mod = this.form.device_mod;
      if (this.form.service) localStorage.service = this.form.service;
      // eslint-disable-next-line no-alert
      alert('Your information will be here when you come back');
    },
  },
};
</script>
