# Witaj na mojej stronie!

To jest moja osobista strona internetowa, na której znajdziesz informacje o mnie, moje portfolio oraz sposób kontaktu ze mną.

## O mnie

Tworzę ilustracje, projekty graficzne, cyfrowe, posługuję się rysunkiem, kolażem i rzeźbię . Często łączę se sobą różne metody i techniki plastyczne.  Staram się w swoich pracach poruszać temety kontrowersjne lub zapomniane przez rutynę dnia codziennego. Uważam, że sztuka powinna otwierać nasze serca i umysły, abyśmy byli bardziej otwarci i podchodzili obiektywnie do niektórych tematów. 

## Portfolio

Poniżej znajdziesz kilka przykładów moich projektów:

### Projekt 1: Strona Portfolio


![Zrzut ekranu](file:///C:/Users/Komputer/Desktop/Portfolio.pdf)


## Kontakt

Jeśli chcesz się ze mną skontaktować, napisz do mnie na adres email: [kla_domagala@o2.pl] 



        .active-tab {
            display: block;
            animation: slideIn 0.5s forwards;
        }

        @keyframes slideIn {
            from {
                transform: translateX(-100%);
            }
            to {
                transform: translateX(0);
            }
        }

        @keyframes slideOut {
            from {
                transform: translateX(0);
            }
            to {
                transform: translateX(-100%);
            }
        }

        /* Dodaj animacje swajpowania dla obsługi przesuwania palcem */
        .tab.touch-slide {
            animation: none;
        }

        .touch-slide.active-tab {
            position: absolute;
            left: 0;
            top: 0;
            animation: none;
        }
    </style>
</head>
<body>

<header>
    <h1>Witaj na mojej witrynie mobilnej!</h1>
</header>

<nav>
    <a href="#" onclick="openTab(event, 'about')">O mnie</a>
    <a href="#" onclick="openTab(event, 'portfolio')">Portfolio</a>
    <a href="#" onclick="openTab(event, 'contact')">Kontakt</a>
</nav>

<section id="about" class="tab active-tab">
    <h2>O mnie</h2>
    <p>Tutaj możesz napisać coś o sobie.</p>
</section>

<section id="portfolio" class="tab">
    <h2>Portfolio</h2>
    <p>Tutaj możesz wyświetlić swoje projekty.</p>
</section>

<section id="contact" class="tab">
    <h2>Kontakt</h2>
    <p>Tutaj możesz umieścić dane kontaktowe.</p>
</section>

<script>
var touchStartX = 0;
var touchEndX = 0;

document.addEventListener('touchstart', function(event) {
    touchStartX = event.changedTouches[0].screenX;
}, false);

document.addEventListener('touchend', function(event) {
    touchEndX = event.changedTouches[0].screenX;
    handleSwipe();
}, false);

function handleSwipe() {
    var swipeThreshold = 50; // Minimalna odległość przesunięcia palcem w pikselach

    if (touchEndX - touchStartX > swipeThreshold) {
        // Swipe w prawo
        var activeTab = document.querySelector('.active-tab');
        var prevTab = activeTab.previousElementSibling;
        if (prevTab && prevTab.classList.contains('tab')) {
            changeTab(prevTab);
        }
    } else if (touchStartX - touchEndX > swipeThreshold) {
        // Swipe w lewo
        var activeTab = document.querySelector('.active-tab');
        var nextTab = activeTab.nextElementSibling;
        if (nextTab && nextTab.classList.contains('tab')) {
            changeTab(nextTab);
        }
    }
}

function openTab(evt, tabName) {
    var tab = document.getElementById(tabName);
    changeTab(tab);
}

function changeTab(tab) {
    var tabs = document.getElementsByClassName("tab");
    for (var i = 0; i < tabs.length; i++) {
        tabs[i].classList.remove("active-tab");
    }
    tab.classList.add("active-tab");
    tab.classList.add("touch-slide");
}
</script>

</body>
</html>
