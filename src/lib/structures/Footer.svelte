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
          <li><a class="links__item" href="/contact">Contact</a></li>
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
    viewBox="0 0 1489 266"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path
      d="M1343.18 198.941V48.9063H1396.79V68.8004C1406.18 51.6694 1421.1 43.6565 1438.51 43.6565C1465.59 43.6565 1488.52 60.5112 1488.52 99.194V198.941H1434.92V109.97C1434.92 93.1153 1428.84 86.484 1417.51 86.484C1405.35 86.484 1396.79 96.431 1396.79 114.391V198.941H1343.18Z"
      fill="#ECECE2"
    />
    <path
      d="M1254.37 198.664C1216.51 198.664 1192.2 168.823 1192.2 121.299C1192.2 71.8397 1217.06 43.6565 1254.37 43.6565C1269.01 43.6565 1280.89 49.7352 1289.46 61.3401V48.9063H1343.06V204.19C1343.06 243.15 1313.77 265.254 1271.5 265.254C1231.71 265.254 1202.14 248.399 1196.89 210.545H1250.5C1251.6 219.94 1260.44 225.19 1270.67 225.19C1281.72 225.19 1289.46 221.321 1289.46 204.467V180.152C1280.61 192.309 1268.73 198.664 1254.37 198.664ZM1268.18 155.837C1282.27 155.837 1289.46 143.956 1289.46 121.299C1289.46 98.6414 1282.27 86.484 1268.18 86.484C1254.37 86.484 1247.18 98.6414 1247.18 121.299C1247.18 143.956 1254.37 155.837 1268.18 155.837Z"
      fill="#ECECE2"
    />
    <path
      d="M1144.01 37.3013V0H1197.61V37.3013H1144.01ZM1144.01 198.94V48.9062H1197.61V198.94H1144.01Z"
      fill="#ECECE2"
    />
    <path
      d="M1060.4 92.2864C1060.4 114.667 1150.2 93.9442 1150.2 151.416C1150.2 182.086 1121.47 204.19 1080.02 204.19C1040.79 204.19 1011.77 187.336 1006.52 149.482H1060.13C1061.23 158.876 1069.8 164.126 1081.4 164.126C1091.63 164.126 1096.6 160.81 1096.6 154.732C1096.6 132.903 1009.29 153.903 1009.29 95.0495C1009.29 68.5241 1030.84 43.6565 1073.39 43.6565C1111.52 43.6565 1140.53 61.0638 1144.68 98.9177H1091.35C1089.42 88.6944 1083.06 83.7209 1072.01 83.7209C1065.38 83.7209 1060.4 87.0366 1060.4 92.2864Z"
      fill="#ECECE2"
    />
    <path
      d="M1017.66 149.482C1010.2 183.744 980.633 204.19 941.95 204.19C893.872 204.19 863.479 173.244 863.479 124.062C863.479 72.9449 894.149 43.6565 940.292 43.6565C986.988 43.6565 1016.55 74.0502 1016.55 123.785V135.39H918.464C920.95 153.074 928.687 162.468 941.95 162.468C951.897 162.468 957.699 158.6 961.567 149.482H1017.66ZM940.292 85.3787C929.24 85.3787 922.332 92.839 919.293 107.207H961.291C958.252 92.839 951.344 85.3787 940.292 85.3787Z"
      fill="#ECECE2"
    />
    <path
      d="M780.187 204.19C742.333 204.19 718.018 173.244 718.018 124.061C718.018 72.9448 742.886 43.6564 780.187 43.6564C794.831 43.6564 806.713 50.0114 815.278 61.8926V0H868.882V198.94H815.278V185.125C806.436 197.559 794.555 204.19 780.187 204.19ZM794.003 161.363C808.094 161.363 815.278 148.376 815.278 124.061C815.278 99.4702 808.094 86.4838 794.003 86.4838C780.187 86.4838 773.003 99.4702 773.003 124.061C773.003 148.376 780.187 161.363 794.003 161.363Z"
      fill="#ECECE2"
    />
    <path
      d="M629.622 198.941V48.9063H683.225V68.5241C692.344 51.1168 705.883 43.6565 719.422 43.6565C725.777 43.6565 731.579 45.3143 734.618 48.9063V93.6679C729.092 92.5627 724.119 92.0101 716.935 92.0101C694.001 92.0101 683.225 103.891 683.225 125.443V198.941H629.622Z"
      fill="#ECECE2"
    />
    <path
      d="M635.783 149.482C628.323 183.744 598.758 204.19 560.075 204.19C511.998 204.19 481.604 173.244 481.604 124.062C481.604 72.9449 512.274 43.6565 558.417 43.6565C605.113 43.6565 634.678 74.0502 634.678 123.785V135.39H536.589C539.076 153.074 546.812 162.468 560.075 162.468C570.022 162.468 575.825 158.6 579.693 149.482H635.783ZM558.417 85.3787C547.365 85.3787 540.457 92.839 537.418 107.207H579.417C576.377 92.839 569.469 85.3787 558.417 85.3787Z"
      fill="#ECECE2"
    />
    <path
      d="M398.313 204.19C360.459 204.19 336.144 173.244 336.144 124.061C336.144 72.9448 361.011 43.6564 398.313 43.6564C412.957 43.6564 424.838 50.0114 433.404 61.8926V0H487.007V198.94H433.404V185.125C424.562 197.559 412.681 204.19 398.313 204.19ZM412.128 161.363C426.22 161.363 433.404 148.376 433.404 124.061C433.404 99.4702 426.22 86.4838 412.128 86.4838C398.313 86.4838 391.129 99.4702 391.129 124.061C391.129 148.376 398.313 161.363 412.128 161.363Z"
      fill="#ECECE2"
    />
    <path d="M287.952 198.94V0H341.556V198.94H287.952Z" fill="#ECECE2" />
    <path
      d="M294.113 149.482C286.653 183.744 257.088 204.19 218.405 204.19C170.328 204.19 139.934 173.244 139.934 124.062C139.934 72.9449 170.604 43.6565 216.747 43.6565C263.443 43.6565 293.008 74.0502 293.008 123.785V135.39H194.919C197.406 153.074 205.142 162.468 218.405 162.468C228.352 162.468 234.155 158.6 238.023 149.482H294.113ZM216.747 85.3787C205.695 85.3787 198.787 92.839 195.748 107.207H237.747C234.707 92.839 227.8 85.3787 216.747 85.3787Z"
      fill="#ECECE2"
    />
    <path
      d="M0 198.94V0H53.6034V68.8003C62.9978 51.6693 77.9184 43.6564 95.3257 43.6564C122.404 43.6564 145.337 60.5111 145.337 99.1939V198.94H91.7337V109.97C91.7337 93.1152 85.6549 86.4839 74.3264 86.4839C62.1689 86.4839 53.6034 96.4309 53.6034 114.391V198.94H0Z"
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
  }

  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgb(255, 136, 0);
    z-index: -1;
    opacity: 0.5;
  }

  .footer__paragraph {
    display: grid;
    grid-template-columns: 1fr 1fr;
    margin-bottom: 15rem;
  }

  .footer__title {
    font-size: var(--font-size-medium);
    font-weight: 100;
    width: 25rem;
    margin: 0;
  }

  .footer__links {
    display: flex;
    gap: 10rem;
    font-weight: 200;
    pointer-events: all;
  }

  .links__list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: var(--gap-small);
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
    bottom: 0;
    right: 0;
    width: 100%;
    fill: var(--light);
    transition: 0.2s;
  }

  .footer__bottom {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: var(--font-size-small);
    font-weight: 200;
    pointer-events: all;
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
