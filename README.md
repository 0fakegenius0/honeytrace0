# honeytrace
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>HoneyTrace - Know Your Honey</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background-color: #fff8e7;
      color: #333;
    }
    header {
      background-color: #f5b942;
      padding: 1.5rem;
      text-align: center;
      color: white;
    }
    header h1 {
      margin: 0;
      font-size: 2.5rem;
    }
    header p {
      margin-top: 0.5rem;
      font-size: 1.2rem;
    }
    .container {
      padding: 2rem;
      max-width: 900px;
      margin: auto;
    }
    .search-banner {
      background: linear-gradient(to right, #f5b942, #ffd26c);
      color: #4a2c00;
      padding: 1rem;
      margin-bottom: 1rem;
      text-align: center;
      font-size: 1.5rem;
      font-weight: bold;
      border-radius: 10px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }
    .search-section input[type="text"] {
      padding: 0.8rem;
      width: 70%;
      font-size: 1rem;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .search-section button {
      padding: 0.8rem 1.2rem;
      font-size: 1rem;
      background-color: #f5b942;
      color: white;
      border: none;
      border-radius: 5px;
      margin-left: 0.5rem;
      cursor: pointer;
    }
    .hero-image {
      margin-top: 2rem;
      text-align: center;
    }
    .hero-image img {
      max-width: 100%;
      height: auto;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    }
    .how-it-works {
      margin-top: 3rem;
    }
    .how-it-works h2 {
      margin-bottom: 1rem;
    }
    .how-it-works ul {
      list-style: none;
      padding: 0;
    }
    .how-it-works li {
      margin-bottom: 1rem;
      background: #fff3cd;
      padding: 1rem;
      border-left: 5px solid #f5b942;
    }
    .farmer-form {
      margin-top: 3rem;
      background-color: #fff3cd;
      padding: 2rem;
      border-radius: 10px;
    }
    .farmer-form h2 {
      margin-bottom: 1rem;
    }
    .farmer-form label {
      display: block;
      margin-top: 1rem;
    }
    .farmer-form input, .farmer-form textarea {
      width: 100%;
      padding: 0.7rem;
      margin-top: 0.5rem;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .farmer-form button {
      margin-top: 1.5rem;
      padding: 0.8rem 1.5rem;
      background-color: #f5b942;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 1rem;
      cursor: pointer;
    }
    #result {
      margin-top: 2rem;
      background: #e2f0cb;
      padding: 1rem;
      border-radius: 8px;
      display: none;
    }
    iframe {
      width: 100%;
      height: 300px;
      border: 0;
      border-radius: 8px;
      margin-top: 1rem;
    }
    footer {
      text-align: center;
      padding: 1.5rem;
      background-color: #f5b942;
      color: white;
    }
  </style>
</head>
<body>
  <header>
    <h1>HoneyTrace</h1>
    <p>Know Your Honey – Verify the Source, Trust the Harvest</p>
  </header>
  <div class="container">
    <div class="search-banner">Know Your Honey 🍯</div>
    <section class="search-section">
      <h2>Search for a Honey Product</h2>
      <input type="text" id="searchInput" placeholder="Enter product name or code..." />
      <button onclick="searchHoney()">Search</button>
    </section>

    <div id="result"></div>

    <div class="hero-image">
      <img src="image.png" alt="Illustration showing a honey jar with QR code, bees, and steps for verifying honey origin using blockchain">
    </div>

    <section class="how-it-works">
      <h2>How It Works</h2>
      <ul>
        <li><strong>Step 1:</strong> Enter the product name or scan the QR code on the honey jar.</li>
        <li><strong>Step 2:</strong> We verify the license of the producer through blockchain records.</li>
        <li><strong>Step 3:</strong> You view where your honey was harvested and who produced it.</li>
      </ul>
    </section>

    <section class="sample">
      <h2>Example Product</h2>
      <p><strong>Product:</strong> GoldenBee Alberta Honey</p>
      <p><strong>License Status:</strong> ✅ Verified by Government of Canada</p>
      <p><strong>Origin:</strong> Alberta, Canada</p>
      <p><strong>Beekeeper:</strong> John Doe (License #CA-458712)</p>
      <p><strong>Batch Number:</strong> GBH-2024-AL-01</p>
      <p><strong>Blockchain Record:</strong> Immutable verification record stored on public blockchain</p>
    </section>

    <section class="farmer-form">
      <h2>Register as a Local Beekeeper</h2>
      <p>Are you a licensed local beekeeper? Submit your details below to be added to the HoneyTrace registry.</p>
      <form onsubmit="alert('Your information has been submitted for review.'); return false;">
        <label for="name">Full Name</label>
        <input type="text" id="name" name="name" required>

        <label for="license">License Number</label>
        <input type="text" id="license" name="license" required>

        <label for="location">Location (City, Province)</label>
        <input type="text" id="location" name="location" required>

        <label for="description">Farm Description</label>
        <textarea id="description" name="description" rows="4"></textarea>

        <button type="submit">Submit</button>
      </form>
    </section>
  </div>
  <footer>
    <p>&copy; 2025 HoneyTrace. Concept demo for educational use only.</p>
  </footer>

  <script>
    function searchHoney() {
      const input = document.getElementById('searchInput').value.trim().toLowerCase();
      const result = document.getElementById('result');

      if (input === 'honeymaid') {
        result.innerHTML = `
          <h3>Honeymaid Prairie Gold</h3>
          <p><strong>License Status:</strong> ✅ Verified by Government of Canada</p>
          <p><strong>Origin:</strong> Saskatoon, Saskatchewan</p>
          <p><strong>Beekeeper:</strong> Mary-Anne Cooper (License #SK-772908)</p>
          <p><strong>Batch Number:</strong> HM-2024-SK-03</p>
          <p><strong>Blockchain Record:</strong> ✔️ Verified and immutable</p>
          <iframe src="https://maps.google.com/maps?q=Saskatoon,%20SK&t=&z=13&ie=UTF8&iwloc=&output=embed"></iframe>
        `;
      } else {
        result.innerHTML = `<p style="color:red;"><strong>Product not found.</strong></p>`;
      }
      result.style.display = 'block';
    }
  </script>
</body>
</html>
