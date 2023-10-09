<script>
    import 'bootstrap/dist/css/bootstrap.min.css';
    let email = 'dddd@email.com';
</script>

<!-- Navbar -->
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
        <a class="navbar-brand" href="#">Radon Tech</a>
    </div>
</nav>

<!-- Main Content -->
<div class="container mt-5 py-5 text-light" style="background-color: #131B26; border-radius: 10px;">
    <!-- About Section -->
    <section class="mb-5">
        <h2 class="display-4">About</h2>
        <p class="lead">Risk Management and Investment Solutions for the Crypto industry.</p>
    </section>

    <!-- Services Section -->
    <section class="mb-5">
        <h2 class="display-4">Services</h2>
        <ul class="list-unstyled mt-4">
            <li class="lead">Risk management and yield enhancement</li>
            <li class="lead">Market making</li>
            <li class="lead">Optimal execution</li>
        </ul>
    </section>

    <!-- Products Section -->
    <section class="mb-5">
        <h2 class="display-4">Products</h2>
        <ul class="list-unstyled mt-4">
            <li class="lead">Covered call</li>
            <li class="lead">Covered put</li>
            <li class="lead">Accumulator</li>
            <li class="lead">Range farmer</li>
        </ul>
    </section>

    <!-- Contact Section -->
    <section class="mb-5">
        <h2 class="display-4">Contact</h2>
        <p class="lead mt-4">Email us at: <a href="mailto:{email}" class="text-info">{email}</a></p>
    </section>
</div>

<!-- Background Image -->
<style>
    body {
        font-family: 'Helvetica', sans-serif;
        color: #F2F2F2;
        background: url('/44.jpg') no-repeat center center fixed;
        background-size: cover;
        margin: 0;
        height: 100vh;
    }

    .display-4 {
        font-size: 2rem;
    }
</style>
