<script>
  import { onMount } from "svelte";

  onMount(() => {
    const footer = document.querySelector(".footer");
    const svg = document.getElementById("mySvg");
    const pageWidth = window.innerWidth;

    footer.addEventListener("mousemove", (event) => {
      const mouseY = event.clientY;
      const relativePosition = mouseY / footer.offsetHeight - 0.4;
      const blurAmount = relativePosition * 30; // Adjust this value to change the maximum blur amount

      svg.style.filter = `blur(${blurAmount}px)`;
    });

    footer.addEventListener("mouseleave", () => {
      svg.style.filter = "none";
    });
  });
</script>

<footer class="footer" id="contact">
  <div class="overlay"></div>
  <div class="footer__container">
    <div class="footer__paragraph">
      <h3 class="footer__title mobile-hide">
        Whether you have a question or a creative challenge, we’re here to help.
        Reach out to us via email or give us a call. We’d love to hear from you!
      </h3>
      <div class="footer__links">
        <ul class="links__navigation links__list">
          <li class="links__item">
            <p class="links__link list__title">navigation</p>
          </li>
          <li><a class="links__item" href="#capsulated">Capsulated </a></li>

          <li><a class="links__item" href="#schermlicht">Schermlicht </a></li>
          <!-- <li><a class="links__item" href="/contact">Contact</a></li> -->
        </ul>

        <ul class="links__contact links__list">
          <li class="links__item">
            <p class="links__link list__title">contact</p>
          </li>
          <li class="links__item">
            <a
              href="mailto:info@helderdesign.studio"
              class="links__link noTransition"
              >info@helderdesign.studio
            </a>
          </li>
          <li class="links__item margin__bottom">
            <a href="tel:+31612345678" class="links__link noTransition"
              >+31 6 42 61 54 78</a
            >
          </li>

          <li class="links__item">
            <p class="links__link">kvk 94349320</p>
          </li>
          <li class="links__item">
            <p class="links__link">btw NL866744319B01</p>
          </li>
        </ul>
      </div>
    </div>
  </div>

  <svg
    class="footer__logo"
    width="1555"
    height="258"
    viewBox="0 0 1555 258"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path
      d="M86.656 55.59C119.144 55.59 140.104 79.17 140.104 115.85V201H91.372V121.614C91.372 105.37 85.608 96.986 72.77 96.986C58.098 96.986 48.928 107.466 48.928 125.544V201H0.196001V8.43H48.928V68.952C59.408 60.568 72.508 55.59 86.656 55.59ZM296.395 128.95C296.395 133.404 296.133 137.596 295.609 142.05H190.547C193.691 158.294 203.909 166.678 219.367 166.678C230.633 166.678 240.327 161.7 244.781 153.316H293.513C283.557 185.542 254.737 205.716 219.367 205.716C175.089 205.716 142.601 173.49 142.601 130.26C142.601 87.03 174.827 55.066 219.367 55.066C264.955 55.066 296.395 87.554 296.395 128.95ZM219.367 93.318C205.219 93.318 195.263 100.916 191.333 115.064H248.449C244.257 100.916 234.039 93.318 219.367 93.318ZM300.227 201V8.43H348.959V201H300.227ZM462.335 8.43H510.543V201H474.649L469.933 190.52C458.405 200.214 443.733 205.978 427.227 205.978C383.997 205.978 353.081 174.276 353.081 130.26C353.081 86.506 383.997 55.066 427.227 55.066C440.327 55.066 452.379 58.472 462.335 64.76V8.43ZM433.777 162.748C452.117 162.748 465.479 148.862 465.479 130.522C465.479 111.92 452.117 98.034 433.777 98.034C415.699 98.034 402.075 111.92 402.075 130.522C402.075 148.862 415.699 162.748 433.777 162.748ZM668.405 128.95C668.405 133.404 668.143 137.596 667.618 142.05H562.557C565.701 158.294 575.919 166.678 591.377 166.678C602.643 166.678 612.337 161.7 616.791 153.316H665.523C655.566 185.542 626.747 205.716 591.377 205.716C547.099 205.716 514.61 173.49 514.61 130.26C514.61 87.03 546.837 55.066 591.377 55.066C636.965 55.066 668.405 87.554 668.405 128.95ZM591.377 93.318C577.228 93.318 567.273 100.916 563.343 115.064H620.459C616.267 100.916 606.049 93.318 591.377 93.318ZM751.36 58.996H764.46V103.536H745.334C728.304 103.536 720.968 111.134 720.968 129.212V201H672.236V59.52H704.986L712.584 75.24C722.54 63.712 734.592 58.996 751.36 58.996ZM863.257 8.43H911.465V201H875.571L870.855 190.52C859.327 200.214 844.655 205.978 828.149 205.978C784.919 205.978 754.003 174.276 754.003 130.26C754.003 86.506 784.919 55.066 828.149 55.066C841.249 55.066 853.301 58.472 863.257 64.76V8.43ZM834.699 162.748C853.039 162.748 866.401 148.862 866.401 130.522C866.401 111.92 853.039 98.034 834.699 98.034C816.621 98.034 802.997 111.92 802.997 130.522C802.997 148.862 816.621 162.748 834.699 162.748ZM1069.33 128.95C1069.33 133.404 1069.06 137.596 1068.54 142.05H963.478C966.622 158.294 976.84 166.678 992.298 166.678C1003.56 166.678 1013.26 161.7 1017.71 153.316H1066.44C1056.49 185.542 1027.67 205.716 992.298 205.716C948.02 205.716 915.532 173.49 915.532 130.26C915.532 87.03 947.758 55.066 992.298 55.066C1037.89 55.066 1069.33 87.554 1069.33 128.95ZM992.298 93.318C978.15 93.318 968.194 100.916 964.264 115.064H1021.38C1017.19 100.916 1006.97 93.318 992.298 93.318ZM1127.65 205.716C1089.14 205.716 1065.82 185.28 1065.3 154.626H1112.2C1112.2 165.106 1119.53 169.822 1128.7 169.822C1135.78 169.822 1142.59 166.154 1142.59 158.818C1142.59 150.696 1131.85 148.338 1118.22 146.242C1096.21 142.574 1067.13 136.024 1067.13 101.702C1067.13 73.406 1091.5 55.066 1127.65 55.066C1163.55 55.066 1187.13 74.192 1187.65 102.75H1141.8C1141.8 93.842 1135.78 89.65 1127.13 89.65C1119.27 89.65 1114.03 93.58 1114.03 100.13C1114.03 107.99 1124.77 110.086 1138.13 112.444C1160.67 116.374 1190.27 121.09 1190.27 156.722C1190.27 186.328 1165.38 205.716 1127.65 205.716ZM1195.03 41.966V0.569988H1243.24V41.966H1195.03ZM1194.77 201V59.52H1243.5V201H1194.77ZM1369.2 59.52L1401.95 59.782V185.542C1401.95 229.82 1372.86 257.33 1326.23 257.33C1286.14 257.33 1258.11 237.156 1251.56 203.62H1298.46C1301.86 213.052 1313.91 218.292 1325.7 218.292C1342.21 218.292 1355.31 207.812 1355.31 191.044V186.852C1344.57 193.402 1331.99 197.332 1318.37 197.332C1277.76 197.332 1247.63 167.202 1247.63 126.33C1247.63 85.982 1277.76 55.066 1318.37 55.066C1335.4 55.066 1350.86 61.354 1362.91 71.572L1369.2 59.52ZM1326.49 157.246C1344.04 157.246 1356.62 144.408 1356.62 126.33C1356.62 108.514 1344.04 95.414 1326.49 95.414C1308.94 95.414 1296.1 108.514 1296.1 126.33C1296.1 144.408 1308.67 157.246 1326.49 157.246ZM1499.88 55.59C1532.63 55.59 1554.37 78.908 1554.37 114.802V201H1505.64V121.614C1505.64 105.108 1499.35 96.986 1487.04 96.986C1471.84 96.986 1463.2 107.466 1463.2 125.544V201H1414.46V59.52H1448.79L1455.34 74.192C1465.82 62.402 1481.54 55.59 1499.88 55.59Z"
      fill="#ECECE2"
    />
  </svg>

  <div class="footer__bottom">
    <p class="bottom__text">© 2024 helderdesign</p>
    <a class="bottom__text noTransition mobile-hide" href="#top"
      >Terms & conditions</a
    >
    <p class="bottom__text">
      Website by <a href="https://studiorolie.com">studiorolie </a>
    </p>
  </div>
</footer>

<style>
  .footer {
    position: relative;
    display: flex;
    justify-content: flex-end;
    flex-direction: column;
    width: 100%;
    height: 80svh;
    padding: var(--padding-large);
    background: none;
    z-index: 200;
    color: var(--light);
    pointer-events: none;
    z-index: 10;
  }

  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgb(76, 169, 255);
    z-index: 1;
    opacity: 0.5;
  }

  .footer__container {
    position: relative;

    z-index: 10;
  }

  .footer__paragraph {
    position: relative;
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin-bottom: 15rem;
    z-index: 10;
  }

  .footer__title {
    position: relative;
    font-size: var(--font-size-medium);
    font-weight: 100;
    width: 25rem;
    margin: 0;
    z-index: 10;
  }

  .footer__links {
    position: relative;
    display: flex;
    gap: 10rem;
    font-weight: 200;
    pointer-events: all;
    z-index: 10;
  }

  .links__list {
    position: relative;
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: var(--gap-small);
    z-index: 10;
  }

  .links__link {
    margin: 0;
    transition: 0.3s;
  }

  a:hover {
    filter: blur(1px);
  }

  .list__title {
    font-size: var(--font-size-small);
    font-weight: 400;
    margin-bottom: var(--margin-small);
  }

  .margin__bottom {
    margin-bottom: var(--margin-small);
  }

  .footer__logo {
    position: relative;
    bottom: 0;
    right: 0;
    width: 100%;
    fill: var(--light);
    transition: 0.2s;
    z-index: 10;
  }

  .footer__bottom {
    position: relative;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: var(--font-size-small);
    font-weight: 200;
    pointer-events: all;
    z-index: 10;
  }

  .bottom__text {
    margin: 0;
  }

  @media (max-width: 768px) {
    .footer {
      height: auto;
      padding: var(--padding-medium);
    }

    .footer__paragraph {
      grid-template-columns: 1fr;
      gap: var(--gap-large);
      margin-bottom: 15rem;
    }

    .footer__title {
      width: 80%;
    }

    .links__navigation {
      display: none;
    }

    .footer__links {
      gap: var(--gap-large);
      margin-top: 0.5rem;
    }

    .footer__logo {
      margin-bottom: 1rem;
      width: 100%;
      height: 200%;
      overflow: visible;
      margin-bottom: 2rem;
    }
  }
</style>
