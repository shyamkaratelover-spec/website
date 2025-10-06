# Ex.07 Restaurant Website
# Date:06/10/2025
# AIM:
To develop a static Restaurant website to display the food items and services provided by them.

# DESIGN STEPS:
## Step 1:
Requirement collection.

## Step 2:
Creating the layout using HTML and CSS.

## Step 3:
Updating the sample content.

## Step 4:
Choose the appropriate style and color scheme.

## Step 5:
Validate the layout in various browsers.

## Step 6:
Validate the HTML code.

## Step 7:
Publish the website in the given URL.

# PROGRAM:
```
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Saffron Spoon - Restaurant Project</title>
  <style>
    :root{
      --primary: #E7634A;
      --secondary: #0E6B66;
      --accent: #FFF6F0;
      --dark: #333333;
      --radius: 12px;
      --maxw: 1100px;
      font-family: Arial, Helvetica, sans-serif;
      color: var(--dark);
      background: linear-gradient(180deg,var(--accent),#fff);
    }
    *{box-sizing:border-box}
    body{margin:0;padding:0;}
    .container{max-width:var(--maxw);margin:0 auto;padding:24px}

    header{background:var(--secondary);color:var(--accent)}
    .nav{display:flex;align-items:center;justify-content:space-between;padding:18px 24px}
    .brand{display:flex;align-items:center;gap:12px}
    .logo{width:48px;height:48px;background:var(--accent);border-radius:10px;display:flex;align-items:center;justify-content:center;font-weight:bold;color:var(--secondary)}
    nav a{color:var(--accent);text-decoration:none;margin-left:18px;font-weight:600}
    nav a:hover{text-decoration:underline}

    .hero{display:grid;grid-template-columns:1fr 420px;gap:24px;align-items:center;padding:48px 24px}
    .hero-card{background:linear-gradient(180deg, rgba(255,255,255,0.95), rgba(255,255,255,0.9));padding:28px;border-radius:var(--radius);box-shadow:0 8px 24px rgba(14,107,102,0.08)}
    .hero h1{margin:0 0 12px 0;font-size:32px;color:var(--primary)}
    .hero p{margin:0 0 18px 0}
    .btn{display:inline-block;padding:10px 16px;border-radius:10px;background:var(--primary);color:#fff;text-decoration:none;font-weight:700}
    .hero-img{border-radius:var(--radius);overflow:hidden;height:280px;display:flex;align-items:center;justify-content:center}

    #menu .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:18px}
    .card{background:#fff;padding:14px;border-radius:12px;box-shadow:0 6px 18px rgba(0,0,0,0.05)}
    .food-img{height:140px;border-radius:10px;background:linear-gradient(135deg,var(--primary),var(--secondary));display:flex;align-items:center;justify-content:center;color:var(--accent);font-weight:700}
    .food-title{margin:10px 0 6px 0;font-weight:700}
    .food-desc{font-size:13px;color:#555;margin:0 0 10px 0}
    .price{font-weight:800;color:var(--secondary)}

    /* ADMIN */
    #admin .people{display:grid;grid-template-columns:repeat(auto-fill,minmax(180px,1fr));gap:18px}
    .person{background:#fff;padding:12px;border-radius:12px;text-align:center}
    .avatar{width:100px;height:100px;margin:0 auto 12px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:28px;font-weight:700;color:var(--accent);background:linear-gradient(135deg,var(--primary),var(--secondary))}
    .role{font-size:13px;color:#666}

    /* CONTACT */
    #contact .contact-card{display:grid;grid-template-columns:1fr 1fr;gap:18px}
    .contact-card div{background:#fff;padding:18px;border-radius:12px}
    .small{font-size:14px;color:#444}

    footer{padding:18px;background:var(--dark);color:#fff;text-align:center;margin-top:28px}

    /* responsive */
    @media (max-width:880px){
      .hero{grid-template-columns:1fr;}
      #contact .contact-card{grid-template-columns:1fr}
    }
  </style>
</head>
<body>
  <header>
    <div class="nav container">
      <div class="brand">
        <div class="logo">SS</div>
        <div>
          <div style="font-weight:800">Saffron Spoon</div>
          <div style="font-size:13px;color:var(--accent);margin-top:4px">Authentic flavours • Fresh ingredients</div>
        </div>
      </div>
      <nav>
        <a href="#home">Home</a>
        <a href="#menu">Menu</a>
        <a href="#admin">Administration</a>
        <a href="#contact">Contact Us</a>
      </nav>
    </div>
  </header>

  <main class="container">
    <!-- HOME (must be exactly like sample page given) -->
    <section id="home" class="hero">
      <div class="hero-card">
        <h1>Welcome to Saffron Spoon</h1>
        <p>Discover handcrafted dishes inspired by coastal and continental flavours. Fresh ingredients, seasonal menu and a warm dining experience.</p>
        <p><strong>Open:</strong> Mon–Sun, 10:00 AM — 11:00 PM</p>
        <a class="btn" href="#menu">Explore Menu</a>
      </div>
      <div class="hero-img" aria-hidden="true">
        <!-- Banner image (changeable) - simple SVG illustration -->
        <svg width="100%" height="100%" viewBox="0 0 600 350" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
          <rect width="100%" height="100%" fill="#FFF6F0"></rect>
          <g transform="translate(40,30)">
            <ellipse cx="260" cy="220" rx="220" ry="90" fill="#FFEDE8"></ellipse>
            <g transform="translate(30,10)">
              <circle cx="120" cy="120" r="80" fill="#E7634A"></circle>
              <rect x="220" y="60" width="160" height="120" rx="12" fill="#0E6B66"></rect>
              <rect x="210" y="200" width="260" height="40" rx="8" fill="#E7634A"></rect>
            </g>
          </g>
        </svg>
      </div>
    </section>

    <!-- MENU -->
    <section id="menu" style="margin-top:28px">
      <h2>Our Menu</h2>
      <p>We display 12 popular items below (you can extend this list as needed).</p>
      <div class="grid">
        <!-- 12 food items -->
        <!-- Each card: image, title, desc, price -->
        <div class="card">
          <img class="food-img" src="grilled salmon.webp" alt="Grilled salmon">
          <div class="food-title">Grilled Salmon</div>
          <div class="food-desc">Grilled salmon is salmon that has been cooked over coals or a gas flame and is one of the oldest fish preparations known. Although salmon has a strong and distinct flavor, many recipes for grilled salmon use a brief marinade beforehand to help accent the taste of the fish.</div>
          <div class="price">₹ 420</div>
        </div>
        <div class="card">
          <img class="food-img" src="pizza.webp" alt="Margherita pizza">
          <div class="food-title">Margherita Pizza</div>
          <div class="food-desc">A margherita pizza is a classic Italian dish that has earned its place as a symbol of simplicity and deliciousness. It consists of a thin crust topped with three basic ingredients: tomato sauce, fresh mozzarella cheese and basil leaves.</div>
          <div class="price">₹ 350</div>
        </div>
        <div class="card">
          <img class="food-img" src="paneer butter.jpg" alt="Butter Masala">
          <div class="food-title">Paneer Butter Masala</div>
          <div class="food-desc">Paneer Mutter Masala is a popular Indian dish made with paneer (Indian cottage cheese) and green peas cooked in a spicy tomato-based sauce. The dish is usually served with naan, roti, or rice. It is a popular vegetarian dish that is often served at our saffaron spoon restaurants.</div>
          <div class="price">₹ 240</div>
        </div>
        <div class="card">
          <img class="food-img" src="burger.jpg" alt="Classic Burger">
          <div class="food-title">Classic Burger</div>
          <div class="food-desc">Burger is one of the fast-food which is now becoming very common in every person's life. Burgers have no age limit. People of all ages can eat burgers. Burgers are affordable and anyone can eat them both at a restaurant and home. Burgers can be made at home, the recipe is very easy.</div>
          <div class="price">₹ 310</div>
        </div>
        <div class="card">
          <img class="food-img" src="salad.jpg" alt="Caesar Salad">
          <div class="food-title">Caesar Salad</div>
          <div class="food-desc">A Caesar salad (also spelled Cesar, César and Cesare), also known as Caesar's salad, is a green salad of romaine lettuce and croutons dressed with lemon juice (or lime juice), olive oil, eggs, Worcestershire sauce, anchovies, garlic, Dijon mustard, Parmesan and black pepper.</div>
          <div class="price">₹ 180</div>
        </div>
        <div class="card">
          <img class="food-img" src="butter chicken.jpg" alt="Butter Chicken">
          <div class="food-title">Butter Chicken</div>
          <div class="food-desc">Butter chicken is a type of curry made from chicken cooked in a spiced tomato and butter (makhan)-based gravy. The gravy is typically known for its rich texture. It is similar to chicken tikka masala, which uses a tomato paste.</div>
          <div class="price">₹ 290</div>
        </div>
        <div class="card">
          <img class="food-img" src="dosa.webp" alt="Masala Dosa">
          <div class="food-title">Masala Dosa</div>
          <div class="food-desc">Masala Dosa is one of the most popular South Indian breakfast dishes served in restaurants and tiffin centres. Dosa is a crepe made using fermented rice and lentil batter. Masala Dosa is one that is crisp, aromatic, flavourful and has a potato masala or spiced seasoned potatoes stuffed in it.</div>
          <div class="price">₹ 120</div>
        </div>
        <div class="card">
          <img class="food-img" src="spaghetti.webp" alt="Spaghetti Aglio">
          <div class="food-title">Spaghetti Aglio</div>
          <div class="food-desc">Spaghetti Aglio e Olio is a classic Italian pasta dish known for its simplicity and bold flavors. Made with just a handful of aromatic ingredients, its name translates to “Spaghetti with Garlic and Oil.”</div>
          <div class="price">₹ 260</div>
        </div>
        <div class="card">
          <img class="food-img" src="tandoori.webp" alt="Tandoori Chicken">
          <div class="food-title">Tandoori Chicken</div>
          <div class="food-desc">Tandoori chicken is a dish made from chicken marinated in yogurt and spices and roasted in a tandoor, a cylindrical clay oven. The dish is now popular worldwide. The modern form of the dish was popularized by the Moti Mahal restaurant in New Delhi, India in the late 1940s.</div>
          <div class="price">₹ 350</div>
        </div>
        
        <div class="card">
          <img class="food-img" src="cold coffee.webp" alt="cold coffee">
          <div class="food-title">cold coffee</div>
          <div class="food-desc">● With lower acidity than hot coffee, cold coffee offers a gentler option for daily enjoyment. ● Surprising health perks include support for metabolism, heart health, and reduced fluid retention. ● Drinking cold coffee can help increase the feeling of fullness, potentially aiding appetite control.</div>
          <div class="price">₹ 150</div>
        </div>                   
          <div class="card">
          <img class="food-img" src="chocolate mousse.jpg" alt="Chocolate Mousse">
          <div class="food-title">Chocolate Mousse</div>
          <div class="food-desc">Chocolate mousse is a decadent dessert that combines the intense flavor of chocolate with a light, fluffy texture. The term "mousse" comes from the French word for "foam," which aptly describes its airy consistency. Typically made with high-quality chocolate, eggs, sugar, and whipped cream, this dessert is both indulgent and versatile.</div>
          <div class="price">₹250</div>"
        </div>
          <div class="card">
          <img class="food-img" src="briyani.webp" alt="Briyani">
          <div class="food-title">Briyani</div>
          <div class="food-desc">Biryani is a fragrant and flavorful rice dish layered with aromatic spices, tender meat or vegetables, and saffron-infused basmati rice. Loved for its rich taste and royal aroma, biryani is a true celebration of Indian cuisine, offering a perfect blend of spices and textures in every bite.<div class="card">
          <div class="price">₹ 450</div>
        </div> 
        </div> 
      </div>
    </section>

    <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Administration</title>
  <style>
    body {
      font-family: 'Poppins', sans-serif;
      margin: 0;
      padding: 20px;
      background-color: #fdfdfd;
    }
    h1 {
      text-align: center;
      color: #333;
      margin-bottom: 30px;
    }
    .team-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 30px;
    }
    .team-card {
      width: 200px;
      text-align: center;
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      padding: 15px;
      transition: transform 0.3s ease;
    }
    .team-card:hover {
      transform: scale(1.05);
    }
    .team-card img {
      width: 100%;
      height: 200px;
      border-radius: 10px;
      object-fit: cover;
    }
    .team-card h3 {
      margin: 10px 0 5px;
      color: #222;
    }
    .team-card p {
      color: #777;
      font-size: 0.9em;
    }
  </style>
</head>
<body>

  <h1>Our Administration Team</h1>

  <div class="team-container">
    <div class="team-card">
      <img src="manager.webp" alt="Admin 1">
      <h3>John Smith</h3>
      <p>Restaurant Manager</p>
    </div>

    <div class="team-card">
      <img src="sopia.webp" alt="Admin 2">
      <h3>Sophia Williams</h3>
      <p>Head Chef</p>
    </div>

    <div class="team-card">
      <img src="ass chef.webp" alt="Admin 3">
      <h3>Michael Brown</h3>
      <p>Assistant Chef</p>
    </div>

    <div class="team-card">
      <img src="emma.webp" alt="Admin 4">
      <h3>Emma Johnson</h3>
      <p>Finance Officer</p>
    </div>

    <div class="team-card">
      <img src="davit.webp" alt="Admin 5">
      <h3>David Lee</h3>
      <p>Marketing Head</p>
    </div>

    <div class="team-card">
      <img src="oliviya.jpg" alt="Admin 6">
      <h3>Olivia Davis</h3>
      <p>HR Manager</p>
    </div>
  </div>

</body>
</html>


    <!-- CONTACT -->
    <section id="contact" style="margin-top:28px">
      <h2>Contact Us</h2>
      <p>Reach out for reservations, feedback or events.</p>
      <div class="contact-card">
        <div>
          <h3>Address</h3>
          <p class="small">Saffron Spoon<br>12 Spice Street, Central City, State - 600001</p>
          <h3>Phone</h3>
          <p class="small">+91 98765 43210</p>
          <h3>Email</h3>
          <p class="small">contact@saffronspoon.example</p>
        </div>
        <div>
          <h3>Send a message</h3>
          <form onsubmit="event.preventDefault();alert('Form sending is disabled in the template.');">
            <div style="margin-bottom:8px"><input required placeholder="Your name" style="width:100%;padding:8px;border-radius:8px;border:1px solid #ddd"></div>
            <div style="margin-bottom:8px"><input required placeholder="Email" style="width:100%;padding:8px;border-radius:8px;border:1px solid #ddd"></div>
            <div style="margin-bottom:8px"><textarea required placeholder="Message" style="width:100%;padding:8px;border-radius:8px;border:1px solid #ddd" rows="5"></textarea></div>
            <button class="btn" style="border:none;cursor:pointer">Send</button>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer>
    Designed and submitted by MAHALAKSHMI MUTHUKUMARAN
  </footer>

  <!-- Lab report (start) -->
  <!-- The following is a printable lab report. Save as lab_report.html or print to PDF. -->
  <section style="display:none" id="lab-report">
  </section>
</body>
</html>
```
# OUTPUT:
<img width="1920" height="1080" alt="Screenshot 2025-10-06 212211" src="https://github.com/user-attachments/assets/bf21f804-bcd7-4e44-8655-95ec1672dc8b" />
<img width="1920" height="1080" alt="Screenshot 2025-10-06 212231" src="https://github.com/user-attachments/assets/dc298865-6ec8-4b1c-b1e6-bae09813a30f" />
<img width="1920" height="1080" alt="Screenshot 2025-10-06 212255" src="https://github.com/user-attachments/assets/f5ddf099-a0b2-48cd-8691-824d5ea6e15b" />




# RESULT:
The program for designing software company website using HTML and CSS is completed successfully.
