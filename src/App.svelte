<script>
    let email = 'dddd@email.com';
</script>

<style>
    body {
        font-family: 'Helvetica', sans-serif;
        color: #F2F2F2;
		background: url('/44.jpg') no-repeat center center fixed;
        background-size: cover; /* This will cover the entire viewport */
        margin: 0;
    }

    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px 50px;
        background-color: #131B26;
        color: #F2F2F2;
    }

    section {
        padding: 50px 0;
        text-align: center;
    }

    a {
        color: #F2F2F2;
        text-decoration: none;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        margin: 10px 0;
    }
</style>

<nav>
    <h1>Radon Tech</h1>
</nav>

<main>
    <!-- About Section -->
    <section>
        <h2>About</h2>
        <p>Risk Management and Investment Solutions for the Crypto industry.</p>
    </section>

    <!-- Services Section -->
    <section>
        <h2>Services</h2>
        <ul>
            <li>Risk management and yield enhancement</li>
            <li>Market making</li>
            <li>Optimal execution</li>
        </ul>
    </section>

    <!-- Products Section -->
    <section>
        <h2>Products</h2>
        <ul>
            <li>Covered call</li>
            <li>Covered put</li>
            <li>Accumulator</li>
            <li>Range farmer</li>
        </ul>
    </section>

    <!-- Contact Section -->
    <section>
        <h2>Contact</h2>
        <p>Email us at: <a href="mailto:{email}">{email}</a></p>
    </section>
</main>
