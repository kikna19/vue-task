<template>
    <div class="container-fluid content">
        <div class="row mt-4 p-2 ">
            <div class="col header">
                <h3> {{specs[0]}}</h3>
            </div>
            <div class="col" v-for="(v,i) in cars" :key="i">
                <div class="specs">
                    <h4>{{v.make}}</h4>
                </div>
            </div>
        </div>
        <div class="row mt-4 p-2">
            <div class="col header">
                <h3> {{specs[1]}}</h3>
            </div>
            <div class="col" v-for="(v,i) in cars" :key="i">
                <div class="card d-flex align-items-center">
                    <img class="card-img-top" style="height:8rem" :src="v.imgUrl" />
                    <div class="card-body">
                        <p class="card-title">{{v.model}}</p>
                    </div>
                </div>
            </div>
        </div>
        <div class="row mt-4 p-2">
            <div class="col header">
                <h3> {{specs[2]}}</h3>
            </div>
            <div class="col" v-for="(v,i) in cars" :key="i">
                <div class="specs">
                    <h4>{{v.years}}</h4>
                </div>
            </div>
        </div>
        <div class="row mt-4 p-2">
            <div class="col header">
                <h3> {{specs[3]}}</h3>
            </div>
            <div class="col" v-for="(v,i) in cars" :key="i">
                <div class="specs">
                    <h4>{{v.engine}}</h4>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'ContentApp',
    data() {
        return {
            specs: [],
            cars: [
                {
                    make: 'audi',
                    model: 'rs7',
                    years: 2018,
                    engine: 'V-8',
                    imgUrl: 'https://hips.hearstapps.com/hmg-prod/images/2017-audi-rs7-1545086136.jpg'
                },
                {
                    make: 'audi',
                    model: 'rs5',
                    years: 2020,
                    engine: 'V-8',
                    imgUrl: 'https://i.ytimg.com/vi/nWUu037D3sg/maxresdefault.jpg'
                },
                {
                    make: 'maserati',
                    model: 'ghibli',
                    years: 2019,
                    engine: 'V-8',
                    imgUrl: 'https://static.cargurus.com/images/site/2019/03/19/17/23/2019_maserati_ghibli-pic-3112695241629892681-1600x1200.png'
                },
                {
                    make: 'maserati',
                    model: 'quattroporte',
                    years: 2022,
                    engine: 'V-8',
                    imgUrl: 'https://media.ed.edmunds-media.com/maserati/quattroporte/2022/oem/2022_maserati_quattroporte_sedan_trofeo_fq_oem_1_1600.jpg'
                },
                {
                    make: 'maserati',
                    model: 'levante',
                    years: 2021,
                    engine: 'V-8',
                    imgUrl: 'https://carsguide-res.cloudinary.com/image/upload/f_auto,fl_lossy,q_auto,t_cg_hero_large/v1/editorial/2021-Maserati-Levante-Trofeo-SUV-grey-1200x800p-%281%29.jpg'
                },
                {
                    make: 'audi',
                    model: 'sq5',
                    years: 2020,
                    engine: 'V-8',
                    imgUrl: 'https://res.cloudinary.com/caradvice/image/private/q_auto/v1599097277/w6np4r3hgxnk8b9mnrum.jpg'
                },

            ]
        }
    },
    mounted() {
        this.specs = [...Object.keys(this.cars[0])];
    }
}
</script>


<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Titan+One&display=swap');
$border-color: rgb(43, 46, 49);

@mixin flex($align, $justify, $dir) {
    display: flex;
    align-items: $align;
    justify-content: $justify;
    flex-direction: $dir;
}

.content {
    padding: 0 5rem 0 5rem;

    h4 {
        text-transform: Capitalize;
    }

    .row {
        @include flex(center, flex-end, row);
        flex-wrap: wrap;
        border-radius: .5rem;
        color: white;
        border: .1rem solid $border-color;
    }

    .col {
        @include flex(center, center, row);
        max-width: 14rem !important;
        border-left: .1rem solid $border-color;
        margin: .5rem;
    }

    .specs {
        display: block;
        text-align: center;
        width: 14rem;
        font-family: 'Comfortaa', cursive;
    }

    .header {
        border: none;
        font-family: 'Dancing Script', cursive;
        letter-spacing: .1rem;
        text-transform: capitalize;
    }

    .card {
        border: none;
        height: auto;
        width: 14rem;
        border: .1rem solid rgb(43, 46, 49);
        background-color: transparent;

        .card-title {
            text-transform: uppercase;
            font-family: 'Titan One', cursive;
            letter-spacing: .1rem;
        }
    }

}

@media (max-width:550px) {
    .content {
        padding: 0 2rem 0 2rem;

        .row {
            flex-direction: column;
        }

        .col {
            border-left: none !important;
            border-bottom: .1rem solid grey;
            margin-top: 1rem;
        }

    }



}
</style>