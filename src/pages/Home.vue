<template>
    <div class="conteiner">
        <q-page-sticky position="top" :offset="[0, 0]">
            <img v 
                src="~assets/images/flower1.png"
                alt="background image"
                class="main-head-background" 
            />
        </q-page-sticky>
        <div class="main-head">
            <div  class="couple-name-container">
                <img src="~assets/images/name.png"
                    alt="nama pengantin"
                    class="name_icon"
                />
            </div>
        </div>
        <div class="celebrate__text-date-container">
                <p class="intro__text">بسم الله الرحمن الرحيم</p>
                <p class="intro__text">السلام عليكم ورحمة الله وبركاته</p>
                <p class="intro__text">Mahasuci Allah telah menciptakan makhluk hidup dengan berpasang-pasangan. Begitu pula manusia. Sungguh besar rahmat dan karunia yang diberikan-Nya kepada keluarga Kami.</p>
                <p class="intro__text">
                Tanpa mengurangi rasa hormat, maka izinkan kami mengundang sekaligus mengharapkan doa restu dari bapak/ibu dan saudara/i dalam acara pernikahan putra putri kami.
                </p>
                <p class="intro__text">-♥- Terimakasih -♥-</p>
            <div class="celebrate__icon-container">
                <!-- <div class="celebrate__icon"></div> -->
                <img src="~assets/images/flower2.png"
                    alt="bunga pengantin"
                    class="celebrate__icon"
                />
            </div>
            <div class="celebrate__text-container">
                <h3 class="celebrate__text">Save the Date</h3>
            </div>
            <h3 class="celebrate__date">Jum'at</h3>
            <h3 class="celebrate__date">6 Agustus 2021</h3>
            <p text-color="black" class="akad-text">AKAD</p>
            <div >
                <q-time v-model="time"
                        readonly
                        color="black"
                />
            </div>
            <h3 class="celebrate__location">Kp. Paniisan/Karoya Rt. 003 Rw. 002 Des. Cikarang Kec. Muncang Kab. Lebak Prov. Banten</h3>
            <img src="~assets/images/map-pin.png"
                 alt="bunga pengantin"
                 class="location__icon"
                 href ="https://www.google.co.id/maps/place/6%C2%B034'52.8%22S+106%C2%B018'26.6%22E/@-6.5813333,106.3052002,17z/data=!3m1!4b1!4m5!3m4!1s0x0:0x0!8m2!3d-6.5813333!4d106.3073889"
            />
            <a href="https://www.google.co.id/maps/place/6%C2%B034'52.8%22S+106%C2%B018'26.6%22E/@-6.5813333,106.3052002,17z/data=!3m1!4b1!4m5!3m4!1s0x0:0x0!8m2!3d-6.5813333!4d106.3073889">
            Lihat Lokasi dalam Peta
            </a>
            <div class="celebrate__count-down row justify-center q-pa-md">
                <div class="count__down-time-container">
                    <div class="time-box">
                        <div class="inline lingkaran_dalam flex-center"
                             :class="`shadow-up-${5}`">
                            <p class="number">0</p>
                            <p class="label">Hari</p>
                        </div>
                    </div>
                    <div class="time-box">
                        <div class="inline lingkaran_dalam flex-center"
                             :class="`shadow-up-${5}`">
                            <p class="number">0</p>
                            <p class="label">Jam</p>
                        </div>
                    </div>
                    <div class="time-box">
                        <div class="inline lingkaran_dalam flex-center"
                             :class="`shadow-up-${5}`">
                            <p class="number">0</p>
                            <p class="label">Menit</p>
                        </div>
                    </div>
                    <div class="time-box">
                        <div class="inline lingkaran_dalam flex-center"
                             :class="`shadow-up-${5}`">
                            <p class="number">0</p>
                            <p class="label">Detik</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <!-- <hr class="hr-section"> -->
        <div class="wedding__gift-section">
            <img class="wedding__gift-icon" 
                 alt="Gift Icon"
                 src="~assets/images/gift-icon.gif"/>
            <p class="weding__gift-title">Wedding Gift</p>
            <p class="weding__gift-subtitle">
            Bagi keluarga dan sahabat yang ingin mengirimkan hadiah, silahkan kirimkan melalui alamat berikut:
            </p>
            <q-btn id="wedding__gtift-button" label="Tampilkan Alamat"  @click="pop = true" />
        </div>
        <div class="footer-container">
            <div class="footer__text">
                <span><i>Dikarenakan situasi pandemi saat ini maka disaran kan untuk mematuhi protokol kesehatan</i></span>
            </div>
        </div>     

        <!-- Menampilkan Alamt -->
        <q-dialog v-model="pop" persistent transition-show="flip-down" transition-hide="flip-up">
            <q-card class="text-black row justify-center q-pa-md">
                <q-bar>
                    <q-bar-title class="q-pt-none">Alamat Pengiriman</q-bar-title>
                </q-bar>
                <q-card-section class="q-pt-none">
                    <br>
                    <p>
                        <span class="gift-text">Dianah</span>
                        <br>
                        <span class="gift-text-address">Kp. Paniisan/Karoya Rt. 003 Rw. 002 Desa Cikarang Kec. Muncang Kab. Lebak Prov. Banten </span>
                        <br>
                        <br>
                        <span class="gift-text">Robi (085782859606)</span>
                        <br>
                        <span class="gift-text-address">Kp. Cipatat Rt. 002 Rw. 006 Desa Kiarapandak Kec. Sukajaya Kab. Bogor Prov. Jawa Barat</span>
                        <br>
                        <br>
                        <i>
                            <span class="gift-text-address">Terimakasih atas kebaikan Bapak/Ibu/Saudara/i sekalian.</span>
                        </i>
                    </p>
                </q-card-section>
                <q-card-section>
                    <q-btn id="Address-button" v-close-popup>Tutup</q-btn>
                </q-card-section>
            </q-card>
        </q-dialog>
    </div>  
</template>

<script>
    import { ref } from 'vue'

    export default {
        setup(){
            return{
                pop: ref(false),
                time: ref('08:30')
            }
        },

        data(){
            return{
                seconds: 0,
                timeStart: false,
                distance: 0
            }
        },

        methods:{
            getTimes(){
                let countDownDate = new Date('2021-08-06 08:30:00').getTime();
                let now = new Date().getTime();
                this.distance = countDownDate - now;
                this.days = Math.floor(this.distance / (1000 * 60 * 60 * 24));
                this.hours = Math.floor((this.distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                this.minutes = Math.floor((this.distance % (1000 * 60 * 60)) / (1000 * 60));
                this.seconds = Math.floor((this.distance % (1000 * 60)) / 1000);
            },

            getSeconds(){
                if(this.timeStart = true){
                    setTimeout(() => {
                        this.seconds -= 1;
                        this.getSeconds();
                    }, 1000)

                    if(this.seconds === 0) {
                        this.seconds = 60;
                        this.minutes -= 1;
                    }

                    if(this.minutes === 0) {
                        this.minutes = 60;
                        this.hours -= 1;
                    }

                    if(this.hours === 0) {
                        this.hours = 24;
                        this.days -= 1;
                    }

                    if(this.days === 0) {
                        this.timeStart = false;
                    }
                }
            }
        },

        created() {
            this.getTimes();
            this.getSeconds();
        },
           
}
</script>