<script>
import heroOne from "../images/desktop-image-hero-1.jpg";
import heroTwo from "../images/desktop-image-hero-2.jpg";
import heroThree from "../images/desktop-image-hero-3.jpg";

import heroMobOne from "../images/mobile-image-hero-1.jpg";
import heroMobTwo from "../images/mobile-image-hero-2.jpg";
import heroMobThree from "../images/mobile-image-hero-3.jpg";

import arrow from "../images/icon-arrow.svg";

const headingContent = ["Discover innovative ways to decorate", "We are available all across the globe", "Manufactured with the best materials"];
const pContent = ["We provide unmatched quality, comfort, and style for property owners across the country. Our experts combine form and function in bringing your vision to life. Create a room in your own style with our collection and make your property a reflection of you and what you love.", "With stores all over the world, it's easy for you to find furniture for your home or place of business. Locally, we’re in most major cities throughout the country. Find the branch nearest you using our store locator. Any questions? Don't hesitate to contact us today.", "Our modern furniture store provide a high level of quality. Our company has invested in advanced technology to ensure that every product is made as perfect and as consistent as possible. With three decades of experience in this industry, we understand what customers want for their home and office."];
const imagesSrc = [heroOne, heroTwo, heroThree];
const mobileImg = [heroMobOne, heroMobTwo, heroMobThree];

let idx = 0;

const incrementIdx = () => {
    if (idx === 2) {
        idx = -1;
    }
    idx++;
}

const decrementIdx = () => {
    if (idx === 0) {
        idx = 3;
    }
    idx--;
}
</script>


<div class="hero" id="home">
    <img class="hero-img" src={imagesSrc[idx]} alt="">
    <section class="hero-content">
        <h1>{headingContent[idx]}</h1>
        <p>{pContent[idx]}</p>
        <div class="cta-container">
            <div class="cta">
                <a id="shop-nav" href="#home">SHOP NOW</a>
                <img src={arrow} alt="">
            </div>
        </div>
        <div class="btns">
            <button on:click={() => decrementIdx()}>
                <svg width="14" height="24" xmlns="http://www.w3.org/2000/svg"><path d="M13 0L1 12l12 12" stroke="#FFF" fill="none" fill-rule="evenodd"/></svg>
            </button>
            <button on:click={() => incrementIdx()}>
                <svg width="14" height="24" xmlns="http://www.w3.org/2000/svg"><path d="M1 0l12 12L1 24" stroke="#FFF" fill="none" fill-rule="evenodd"/></svg>
            </button>
        </div>
    </section>
</div>

<style>

.hero-content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: relative;
    padding-bottom: 2em;
}

.hero-content h1, .hero-content p, .cta-container {
    width: 80%;
    margin-inline: auto;
}

.btns {
    display: flex;
    position: absolute;
}

.btns button {
    background: black;
    border-style: none;
    padding: 0.8em 1.6em;
    transition: all 0.5s cubic-bezier(0.19, 1, 0.22, 1);
}

.btns button:hover {
    background: #444444;
    cursor: pointer;
}

.cta {
    max-width: fit-content;
    transition: all 0.5s cubic-bezier(0.19, 1, 0.22, 1);
}

.cta > * {
    display: inline;
}

#shop-nav {
    font-size: 15px;
    margin-right: 1em;
    letter-spacing: 12.5px;
    text-decoration: none;
    color: black;
}

.cta:hover {
    filter: opacity(0.5);
    cursor: pointer;
}

@media (max-width: 50em) {

    .hero-content h1 {
        letter-spacing: -1.67px;
    }

    .btns {
        top: 0;
        right: 0;
        z-index: 1;
        transform: translateY(-2.9em);
    }
}

@media (min-width: 50em) {
    .hero {
    display: flex;
}

    .hero-content h1, .hero-content p, .cta-container {
        width: 60%;
    }

    .btns {
        bottom: 0;
    }

    .btns button {
        padding: 2em 2.6em;
    }
}
</style>