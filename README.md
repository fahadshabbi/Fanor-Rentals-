<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fanor Rentals</title>
    <style>
        /* General Styles */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            line-height: 1.6;
            background: linear-gradient(to right, #1f1f1f, #ff0000);
            color: #fff;
        }

        .header {
            background: #2C2C2C;
            color: #fff;
            padding: 20px 0;
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
        }

        .header .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
        }

        .nav ul {
            list-style: none;
            display: flex;
            gap: 15px;
        }

        .nav a {
            color: #fff;
            text-decoration: none;
            padding: 5px 10px;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        .nav a:hover {
            background-color: #f10606;
            color: #2C2C2C;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            background: url('hero.jpg') no-repeat center center/cover;
            color: #fff;
            padding: 100px 20px;
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 20px;
        }

        .search-form input,
        .search-form select,
        .search-form button {
            padding: 15px;
            margin: 10px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }

        .search-form button {
            background: #ff0000;
            color: #fff;
            cursor: pointer;
        }

        /* Catalog Section */
        .catalog {
            padding: 60px 20px;
            background-color: #fff;
            color: #333;
        }

        .catalog h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 40px;
        }

        .car-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
        }

        .car-card {
            background: #fafafa;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .car-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .car-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .car-card h3 {
            text-align: center;
            margin: 10px 0;
        }

        .car-card p {
            text-align: center;
            font-size: 1.1rem;
            margin-bottom: 15px;
        }

        .car-card button {
            display: block;
            width: 100%;
            background: #ff0000;
            color: #fff;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .car-card button:hover {
            background-color: #2C2C2C;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: #fff;
            padding: 40px;
            border-radius: 10px;
            width: 600px;
            max-width: 90 %;
        }

        .modal-content h2 {
            text-align: center;
            font-size: 2rem;
        }

        .modal-content p {
            font-size: 1.1rem;
            margin-bottom: 15px;
        }

        .modal-content button {
            display: block;
            width: 100%;
            background: #ff0000;
            color: #fff;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .modal-content button:hover {
            background-color: #2C2C2C;
        }

        /* About Section */
        .about {
            background: #2C2C2C;
            color: #fdf9f9;
            padding: 60px 20px;
            text-align: center;
        }

        .about h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        /* Footer */
        footer {
            background: #2C2C2C;
            color: #fff;
            text-align: center;
            padding: 20px 0;
        }

        .footer-socials {
            list-style: none;
            display: flex;
            gap: 15px;
            justify-content: center;
            margin: 10px 0;
        }

        .footer-socials a {
            color: #fff;
            font-size: 1.5rem;
            text-decoration: none;
        }

        /* Login and Signup Styles */
        .modal-login-signup {
            width: 400px;
            padding: 30px;
        }

        .modal-login-signup input {
            width: 90%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #2b2626;
        }

        .modal-login-signup button {
            width: 90%;
            padding: 10px;
            background-color: #ff0000;
            border: none;
            color: rgb(16, 13, 13);
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="container">
            <h1>Fanor Rentals</h1>
            <nav class="nav">
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#catalog">Catalog</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#contact">Contact Us</a></li>
                    <li><a href="#" id="login-btn">Login</a></li>
                    <li><a href="#" id="signup-btn">Signup</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <h2>Find Your Perfect Ride</h2>
        <p>"Explore our diverse fleet of cars, perfectly tailored to match your needs and elevate your journey!"</p>
        <form id="search-form" class="search-form" onsubmit="event.preventDefault();">
            <input type="text" placeholder="Search by car name or type..." name="search">
            <select name="type">
                <option value="">All Types</option>
                <option value="suv">SUV</option>
                <option value="sedan">Sedan</option>
                <option value="luxury">Luxury</option>
                <option value="electric">Electric</option>
            </select>
            <button type="submit">Search</button>
        </form>
    </section>

    <!-- Catalog Section -->
    <section id="catalog" class="catalog">
        <h2>OUR FLEET</h2>
        <div class="car-grid">
            <!-- Existing Car Cards -->
            <div class="car-card">
                <img src="https://images.prismic.io/ospreyaad/Zk9Khyol0Zci9ZL0_TeslaModel3Performance-blurred.png?auto=format,compress&w=1200&h=800" alt="Tesla Model 3">
                <h3>Tesla Model 3</h3>
                <p>Price: $90/day</p>
                <button onclick="showCarDetails('Tesla Model 3', 'Electric sedan with autopilot, spacious, and fast.', '$90/day', 'Details about Tesla Model 3')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://stimg.cardekho.com/images/carexteriorimages/930x620/BMW/X5-2023/10452/1688992642182/front-left-side-47.jpg" alt="BMW X5">
                <h3>BMW X5</h3>
                <p>Price: $120/day</p>
                <button onclick="showCarDetails('BMW X5', 'Luxury SUV with powerful engine and spacious interior.', '$120/day', 'Details about BMW X5')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://www.carandbike.com/_next/image?url=https%3A%2F%2Fc.ndtvimg.com%2Frange-rover-sport_625x300_1530181391799.jpg&w=3840&q=75" alt="Range Rover">
                <h3>Range Rover</h3>
                <p>Price: $130/day</p>
                <button onclick="showCarDetails('Range Rover', 'Luxury SUV designed for performance and off-road capability.', '$130/day', 'Details about Range Rover')">View Details</button>
            </div>
            <!-- New Car Cards -->
            <div class="car-card">
                <img src="https://www.topgear.com/sites/default/files/cars-car/image/2021/03/audiuk0002282120audi20a420saloon.jpg" alt="Audi A4">
                <h3>Audi A4</h3>
                <p>Price: $85/day</p>
                <button onclick="showCarDetails('Audi A4', 'Compact executive car with a stylish design.', '$85/day', 'Details about Audi A4')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://cdn.jdpower.com/JDPA_2020%20Mercedes-AMG%20C63%20S%20Selenite%20Gray%20Front%20View.jpg" alt="Mercedes-Benz C-Class">
                <h3>Mercedes-Benz C-Class</h3>
                <p>Price: $100/day</p>
                <button onclick="showCarDetails('Mercedes-Benz C-Class', 'Luxury sedan with advanced technology and comfort.', '$100/day', 'Details about Mercedes-Benz C-Class')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://imgd-ct.aeplcdn.com/664x415/cw/ec/23766/Ford-Mustang-Left-Front-Three-Quarter-74324.jpg?v=201711021421&q=80" alt="Ford Mustang">
                <h3>Ford Mustang</h3>
                <p>Price: $110/day</p>
                <button onclick="showCarDetails('Ford Mustang', 'Iconic sports car with powerful performance.', '$110/day', 'Details about Ford Mustang')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://renty.ae/cdn-cgi/image/format=auto,fit=contain,width=816,height=516,sharpen=0/https://renty.ae/uploads/car/photo/l/silver-grey_chevrolet-camaro-v-rs_2023_5565_main_15a51e4b988418c01018836a39b706f6.jpg" alt="Chevrolet Camaro">
                <h3>Chevrolet Camaro</h3>
                <p>Price: $105/day</p>
                <button onclick="showCarDetails('Chevrolet Camaro', 'Muscle car with aggressive styling and performance.', '$105/day', 'Details about Chevrolet Camaro')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://di-honda-enrollment.s3.amazonaws.com/2021/model-pages/accord/hero.jpg" alt="Honda Accord">
                <h3>Honda Accord</h3>
                <p>Price: $75/day</p>
                <button onclick="showCarDetails('Honda Accord', 'Reliable sedan with spacious interior and great fuel efficiency.', '$75/day', 'Details about Honda Accord')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://www.motortrend.com/files/67044b22780fb00008f3b63c/001-2025-toyota-camry-xle-lead.jpg?w=768&width=768&q=75&format=webp" alt="Toyota Camry">
                <h3>Toyota Camry</h3>
                <p>Price: $80/day</p>
                <button onclick="showCarDetails('Toyota Camry', 'Comfortable sedan with a reputation for reliability.', '$80/day', 'Details about Toyota Camry')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://vehicle-images.dealerinspire.com/2873-110007342/1N4BL4CV0RN395995/0cfbe0cea150b1e557378d4f9f1679a0.jpg" alt="Nissan Altima">
                <h3>Nissan Altima</h3>
                <p>Price: $70/day</p>
                <button onclick="showCarDetails('Nissan Altima', 'Stylish sedan with advanced safety features.', '$70/day', 'Details about Nissan Altima')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://cdn.jdpower.com/ArticleImages/2019%20Kia%20Optima%2013750_720.jpg" alt="Kia Optima">
                <h3>Kia Optima</h3>
                <p>Price: $65/day</p>
                <button onclick="showCarDetails('Kia Optima', 'Affordable sedan with a spacious interior.', '$65/day', 'Details about Kia Optima')">View Details</button>
            </div>
            <div class="car-card">
 <img src="https://www.autoblog.com/.image/t_share/MjA5MDg5NjkxNzAyMDc3MDQw/2024-hyundai-sonata-hybrid.jpg" alt="Hyundai Sonata">
                <h3>Hyundai Sonata</h3>
                <p>Price: $68/day</p>
                <button onclick="showCarDetails('Hyundai Sonata', 'Stylish sedan with a comfortable ride and modern features.', '$68/day', 'Details about Hyundai Sonata')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://car-images.bauersecure.com/wp-images/152691/49-subaru-outback-review.jpg" alt="Subaru Outback">
                <h3>Subaru Outback</h3>
                <p>Price: $90/day</p>
                <button onclick="showCarDetails('Subaru Outback', 'Versatile wagon with all-wheel drive and off-road capability.', '$90/day', 'Details about Subaru Outback')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://assets.volkswagen.com/is/image/volkswagenag/VW_NGW6_Showroom_GLI_Masthead?Zml0PWNyb3AsMSZmbXQ9cG5nLWFscGhhJndpZD0xNjAwJmhlaT05MDAmYmZjPW9mZiY5YWYy" alt="Volkswagen Jetta">
                <h3>Volkswagen Jetta</h3>
                <p>Price: $75/day</p>
                <button onclick="showCarDetails('Volkswagen Jetta', 'Compact sedan with a fun-to-drive nature and good fuel economy.', '$75/day', 'Details about Volkswagen Jetta')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://images.carexpert.com.au/resize/3000/-/app/uploads/2024/01/2024-Mazda-6-G35-GT-SP-review-4.jpg" alt="Mazda 6">
                <h3>Mazda 6</h3>
                <p>Price: $85/day</p>
                <button onclick="showCarDetails('Mazda 6', 'Stylish midsize sedan with sporty handling and a premium interior.', '$85/day', 'Details about Mazda 6')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://pictures.dealer.com/m/motorworldchryslercllc/1697/25486cc35fea539bfb0fad10c752b8a8x.jpg" alt="Chrysler 300">
                <h3>Chrysler 300</h3>
                <p>Price: $95/day</p>
                <button onclick="showCarDetails('Chrysler 300', 'Full-size sedan with a bold design and spacious interior.', '$95/day', 'Details about Chrysler 300')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://static.overfuel.com/dealers/trust-auto/image/Used-Dodge-Charger.jpg" alt="Dodge Charger">
                <h3>Dodge Charger</h3>
                <p>Price: $110/day</p>
                <button onclick="showCarDetails('Dodge Charger', 'Powerful sedan with muscle car performance and aggressive styling.', '$110/day', 'Details about Dodge Charger')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://www.usnews.com/object/image/00000190-b819-d3cb-abd6-f99d92560001/01-usnpx-jeepwrangler-angularfront-jmv.JPG?update-time=1721075706144&size=responsive640" alt="Jeep Wrangler">
                <h3>Jeep Wrangler</h3>
                <p>Price: $120/day</p>
                <button onclick="showCarDetails('Jeep Wrangler', 'Iconic off-road SUV with rugged capabilities and open-air driving.', '$120/day', 'Details about Jeep Wrangler')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://www.topgear.com/sites/default/files/cars-car/image/2024/02/pcgb20_0589_fine.jpg" alt="Porsche 911">
                <h3>Porsche 911</h3>
                <p>Price: $250/day</p>
                <button onclick="showCarDetails('Porsche 911', 'Legendary sports car with exceptional performance and handling.', '$250/day', 'Details about Porsche 911')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://www.lexusofparramatta.com.au/-/media/lexus/dealers/nsw/parramatta/blog/2022/evolution-of-the-lexus-rx/lexus-rx.png?rev=206158b4a29f4b62a502a5ca025f9f44" alt="Lexus RX">
                <h3>Lexus RX</h3>
                <p>Price: $150/day</p>
                <button onclick="showCarDetails('Lexus RX', 'Luxury SUV with a smooth ride and high-end features.', '$150/day', 'Details about Lexus RX')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://assets.bwbx.io/images/users/iqjWHBFdfxIU/i9GkFjKH5Idg/v2/-1x-1.webp" alt="Tesla Model X">
                <h3>Tesla Model X</h3>
                <p>Price: $150/day</p>
                <button onclick="showCarDetails('Tesla Model X', 'Electric SUV with impressive range and unique falcon-wing doors.', '$150/day', 'Details about Tesla Model X')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://www.autocar.co.uk/sites/autocar.co.uk/files/volvo-xc90-001.jpg" alt="Volvo XC90">
                <h3>Volvo XC90</h3>
                <p>Price: $140/day</p>
                <button onclick="showCarDetails('Volvo XC90', 'Luxury SUV with advanced safety features and spacious interior.', '$140/day', 'Details about Volvo XC90')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://www.cnet.com/a/img/resize/b21f155fd825539e4b511d7c8b74b2d8c920ef95/hub/2017/02/14/d19578aa-f71a-466a-b1b3-ba02783fa1d2/2017-land-rover-discovery-29.jpg?auto=webp&width=768" alt="Land Rover Discovery">
                <h3>Land Rover Discovery</h3>
                <p>Price: $160/day</p>
                <button onclick="showCarDetails('Land Rover Discovery', 'Versatile SUV with off-road capabilities and luxury features.', '$160/day', 'Details about Land Rover Discovery')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://hips.hearstapps.com/hmg-prod/images/2025-infiniti-qx60-autograph-awd-107-6706d8b961188.jpg?crop=0.740xw:0.832xh;0.114xw,0.115xh&resize=768:*" alt="Infiniti QX60">
                <h3>Infiniti QX60</h3>
                <p>Price: $130/day</p>
                <button onclick="showCarDetails('Infiniti QX60', 'Luxury midsize SUV with a comfortable ride and spacious seating.', '$130/day', 'Details about Infiniti QX60')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://hips.hearstapps.com/hmg-prod/images/2025-acura-mdx-105-6685c529159c2.jpg?crop=0.706xw:0.793xh;0.241xw,0.0852xh&resize=768:*" alt="Acura MDX">
                <h3>Acura MDX</h3>
                <p>Price: $125/day</p>
                <button onclick="showCarDetails('Acura MDX', 'Luxury SUV with three rows of seating and advanced technology.', '$125/day', 'Details about Acura MDX')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://media.ed.edmunds-media.com/buick/enclave/2024/oem/2024_buick_enclave_4dr-suv_avenir_fq_oem_1_1280.jpg" alt="Buick Enclave">
                <h3>Buick Enclave</h3>
                <p>Price: $120/day</p>
                <button onclick="showCarDetails('Buick Enclave', 'Spacious SUV with a comfortable interior and family-friendly features.', '$120/day', 'Details about Buick Enclave')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://bucket.dealervenom.com/2024/01/JU0DWZ1m-2023-chrysler-pacifica-carbuzz-930201-1600.jpg?fm=pjpg&ixlib=php-3.3.1" alt="Chrysler Pacifica">
                <h3>Chrysler Pacifica</h3>
                <p>Price: $110/day</p>
                <button onclick="showCarDetails('Chrysler Pacifica', 'Versatile minivan with family-friendly features and ample cargo space.', '$110/day', 'Details about Chrysler Pacifica')">View Details</button>
            </div>
            <div class="car-card">
                <img src="https://garagemmaster.com.br/wp-content/uploads/2024/05/Nova-Picape-Toyota-Rav4-2025-1.webp" alt="Toyota RAV4">
                <h3>Toyota RAV4</h3>
                <p>Price: $95/day</p>
                <button onclick="showCarDetails('Toyota RAV4', 'Compact SUV with a reputation for reliability and versatility.', '$95/day', 'Details about Toyota RAV4')">View Details</button>
            </div>
        </div>
    </section>
    

    <!-- About Section -->
    <section id="about" class="about">
        <h2>About Fanor Rentals</h2>
        <p>At [Fanor Rentals ], we believe your journey begins the moment you get behind the wheel. Whether you're planning a road trip, need a reliable ride for a business trip, or simply want to explore the city in style, we offer a diverse fleet of well-maintained vehicles to meet your needs. With competitive prices, flexible rental terms, and excellent customer service, we make renting a car easy and hassle-free. Let us provide the perfect vehicle for your next adventure—book with us today and experience the freedom of the road like never before!.</p>
    </section>

    <!-- Footer -->
    <footer>
        <ul class="footer-socials">
            <li><a href="#">Facebook =    'Fanor@Rentals'    </a></li>
            <li><a href="#">Twitter  =    'Fanor@Rentals'    </a></li>
            <li><a href="#">Instagram=    'Fanor@Rentals'       </a></li>
        </ul>
        <p>&copy; 2024 Fanor Rentals. All rights reserved.</p>
    </footer>

    <!-- Modal for Car Details -->
    <div id="car-modal" class="modal">
        <div class="modal-content">
            <h2 id="car-name"></h2>
            <p id="car-description"></p>
            <p id="car-price"></p>
            <button onclick="bookNow()">Book Now</button>
            <button onclick="closeModal()">Close</button>
        </div>
    </div>

    <!-- Login Modal -->
    <div id="login-modal" class="modal">
        <div class="modal-content modal-login-signup">
            <h2>Login</h2>
            <input type="text" placeholder="Username">
            <input type="password" placeholder="Password">
            <button onclick="login()">Login</button>
        </div>
    </div>

    <!-- Signup Modal -->
    <div id="signup-modal" class="modal">
        <div class="modal-content modal-login-signup">
            <h2>Signup</h2>
            <input type="text" placeholder="Username">
            <input type="email" placeholder="Email">
            <input type="password" placeholder="Password">
            <button onclick="signup()">Signup</button>
        </div>
    </div>

    <script>
        // Show Car Details in Modal
        function showCarDetails(name, description, price, details) {
            document.getElementById('car-name').textContent = name;
            document.getElementById('car-description').textContent = description;
            document.getElementById('car-price').textContent = price;
            document.getElementById('car-modal').style.display = 'flex';
        }

        // Close Car Details Modal
        function closeModal() {
            document.getElementById('car-modal').style.display = 'none';
        }

        // Book Now (Alert Placeholder)
        function bookNow() {
            alert("Booking functionality coming soon!");
        }

        // Open Login Modal
        document.getElementById('login-btn').onclick = function() {
            document.getElementById('login-modal').style.display = 'flex';
        }

        // Open Signup Modal
        document.getElementById('signup-btn').onclick = function() {
            document.getElementById('signup-modal').style.display = 'flex';
        }

        // Close Modals on Click Outside
        window.onclick = function(event) {
            if (event.target.classList.contains('modal')) {
                closeModal();
                document.getElementById('login-modal').style.display = 'none';
                document.getElementById('signup-modal').style.display = 'none';
            }
        }

        // Functions for Login/Signup
        function login() {
            alert("Login functionality coming soon!");
        }

        function signup() {
            alert("Signup functionality coming soon!");
        }

    </script>
</body>
</html>
