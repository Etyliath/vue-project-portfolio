<template>
    <footer class="footer">
        <div class="footer__copyright">
            <small>copyright Edouard DA SILVA</small>
        </div>
        <div class="footer__social">
            <a href="https://www.linkedin.com/" target="_blank"><img src="/images/linkedin.png" alt="Linkedin"
                    class="reseaux__linkedin"></a>
            <a href="https://twitter.com/" target="_blank"><img src="/images/twitter.png" alt="twitter"
                    class="reseaux__twitter"></a>
            <a href="http://github.com/" target="_blank"><img src="/images/signe-github.png" alt="GitHub"
                    class="reseaux__github"></a>
        </div>
        <div class="footer__publish">
            <small>publié : <time datetime="2023-09-09"> 09 septembre 2023 </time></small>
        </div>
    </footer>
</template>
<style scoped>
.footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    margin-top: auto;
    padding: 0 0.8em 0;
    border-top: 2px solid var(--primary-border-color);
    background: linear-gradient(var(--primary-bg-color), 60%, var(--secondary-bg-color));
}

.footer__copyright {
    color: var(--primary-text-color);
}

.footer__social {
    display: flex;
    justify-content: space-between;
}

.footer__social a {
    text-decoration: none;
    line-height: 0.7em;
    padding: 1em ;
}
.footer__social img{
    width: 50px;
}

.footer__publish {
    color: var(--primary-text-color);
}
</style>