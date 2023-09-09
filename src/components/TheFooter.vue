<template>
    <div class="footer">
        <div class="copyright">
            <small>copyright Edouard DA SILVA</small>
        </div>
        <div class="social">
            <a href="https://www.linkedin.com/" target="_blank"><img src="../assets/images/linkedin.png" alt="Linkedin"
                    class="reseaux__linkedin"></a>
            <a href="https://twitter.com/" target="_blank"><img src="../assets/images/twitter.png" alt="twitter"
                    class="reseaux__twitter"></a>
            <a href="http://github.com/" target="_blank"><img src="../assets/images/signe-github.png" alt="GitHub"
                    class="reseaux__github"></a>
        </div>
        <div class="publish">
           <small>publié : <time datetime="2023-09-09"> 09 septembre 2023 </time></small> 
        </div>
    </div>
</template>
<style>
.footer {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin: 0;
    border-top: 2px solid rgba(94, 148, 202, 0.8);
    background: linear-gradient(rgba(94, 148, 202, 0.6), 80%, rgba(76, 135, 106, 0.6));
}

.copyright {
   color: white;
}

.social {
    display: flex;
    justify-content: space-between;
}

.social a {
    text-decoration: none;
    line-height: 0.7em;
    padding: 1em 1em;
}
.publish{
    color: white;
}
</style>