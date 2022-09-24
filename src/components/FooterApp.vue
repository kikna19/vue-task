<template>
    <div class="container-fluid mt-5 footer">
        <div class="col">
            <h2>more sedans</h2>
            <p class="more">mercedes benz</p>
            <p class="more">dodge</p>
            <p class="more">alfa romeo</p>
        </div>
        <div class="col">
            <h2>more SUVS</h2>
            <p class="more">alfa romeo</p>
            <p class="more">land rover</p>
            <p class="more">jaguar</p>
        </div>
        <div class="col">
            <h2>motocycles</h2>
            <p class="more">BMW S1000RR</p>
            <p class="more">yamaha </p>
            <p class="more">Kawasaki h2</p>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            footerItem: document.getElementsByClassName('more'),
        }
    },
    mounted() {

        const items = Object.values(this.footerItem);
        items.forEach(el => {
            const line = document.createElement('span');
            line.style.display = 'block';
            line.style.height = '0.01rem';
            line.style.width = 'auto';
            line.style.backgroundColor = '#b964f3';
            el.appendChild(line)
        })

    }
}
</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lobster&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Damion&display=swap');

@mixin flex($align, $justify, $dir) {
    display: flex;
    align-items: $align;
    justify-content: $justify;
    flex-direction: $dir;
}

.footer {
    @include flex(flex-start, space-between, row);
    flex-wrap: wrap;
    padding: 2rem 10rem 0 10rem;
    height: 12rem;
    border-top: .1rem solid #b964f3;


    div {
        @include flex(center, center, column);
        width: 15rem;
        color: white;

        h2 {
            font-family: 'Lobster', cursive;
            text-transform: capitalize;
            font-size: 1.3rem;
            letter-spacing: .2rem;
        }

        p {
            font-family: 'Damion', cursive;
            text-transform: capitalize;
            font-size: 1.2rem;
            cursor: pointer;
        }
    }
}

.footer-bottom {
    display: block;
    line-height: 4rem;
    text-align: center;
    width: 100%;
    height: 4rem;

    p {
        font-family: 'Lobster', cursive;
        font-size: 1.3rem;
        letter-spacing: .2rem;
        color: grey;
        text-transform: capitalize;
    }
}

@media (max-width: 1060px) {
    .footer {
        padding: 3rem 5rem 0 5rem;
    }
}

@media (max-width: 900px) {
    .footer {
        padding: 3rem 2rem 0 2rem;
    }
}

@media (max-width: 800px) {
    .footer {
        @include flex(center, flex-start, column);
        height: auto;

        div {
            margin-top: 2rem;


            h2 {
                font-size: 1.1rem;
            }

            p {
                font-size: 1rem;
            }
        }
    }

}
</style>