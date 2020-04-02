<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark sticky-top">
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
            <ul class="navbar-nav">
                <li class="nav-item active">
                    <a class="nav-link" href="#">Profile</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Experience</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Skills</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Projects</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Contact</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Resume</a>
                </li>
            </ul>
        </div>
    </nav>
</template>

<script>
module.exports = {
    props: ["current"]
}
</script>

<style>
@media (min-width: 768px) {
    .navbar {
        position: sticky;
        width: 100vw;
    }

    .navbar .navbar-nav {
        margin-left: 50%;
        transform: translateX(-50%);
        text-align: center;
    }

    .navbar .navbar-collapse {
        text-align: center;
    }
}
@media (max-width: 768px) {
    .navbar-toggler {
        transform: translateX(-50%);
        left: 48vw;
        position: relative;
    }
}
</style>