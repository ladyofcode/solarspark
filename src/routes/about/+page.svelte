<script>
    import frame from '$lib/assets/images/DoorFrameLight.png';
    import tabs from '$lib/assets/images/team/tabs.jpg';
</script>

<section class="header">
    <h1>About</h1>
</section>

<section class="container">
    <p>
        Solarpsark is a Canberra-based studio building games and web experiences. We're still in an experimental phase, being so new, so be sure to check out our socials and streams as we update them.
    </p>

    <p>
        We've been rather inspired by the Solarpunk movement and its associated values. We embrace the idea of a sustainable future where tech and nature exist in harmony. This requires innovation and perhaps venturing into places where no one would normally - something we intend to do in the future.
    </p>
</section>

<section class="container">
    <h2>Team</h2>

    <div id="cards">
        <div class="profile-card">
            <img class="moulding" src={frame} alt="">
            <div class="portrait-container">
                <div class="portrait-container-inner">
                    <img src={tabs} alt="">
                </div>
            </div>
            <h3>Tabs</h3>
            <p>Dev & design</p>
            <div class="socials">
                <a href="https://twitch.tv/ladyofcode">
                    <svg>
                        <use xlink:href="#twitch" />
                    </svg>
                </a>
                <a href="https://instagram.com/ladyofcode">
                    <svg>
                        <use xlink:href="#instagram" />
                    </svg>
                </a>
                <a href="https://twitter.com/ladyofcode">
                    <svg>
                        <use xlink:href="#twitter" />
                    </svg>
                </a>
                <a href="https://ladyofcode.com">
                    <svg>
                        <use xlink:href="#globe" />
                    </svg>
                </a>
            </div>
        </div>
        
    </div>
</section>