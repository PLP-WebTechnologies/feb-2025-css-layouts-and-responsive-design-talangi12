<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Layout with Flexbox</title>
    <style>
        body {
            font-family: sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }

        /* Navigation Bar */
        nav {
            background-color: #333;
            color: white;
            padding: 1em;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        nav .logo {
            font-size: 1.5em;
            font-weight: bold;
        }

        nav ul {
            list-style: none;
            padding: 0;
            margin: 0;
            display: flex;
        }

        nav ul li {
            margin-left: 1em;
        }

        nav ul li a {
            color: white;
            text-decoration: none;
        }

        
        .container {
            display: flex;
            flex-wrap: wrap; /* Allow items to wrap on smaller screens */
            padding: 20px;
            gap: 20px; /* Space between container items */
        }

        .sidebar {
            background-color: #ddd;
            padding: 20px;
            /* Default width for desktop */
            flex: 0 0 25%;
        }

        .main-content {
            background-color: white;
            padding: 20px;
            /* Default width for desktop */
            flex: 1 0 70%; /* Grow to fill available space, initial width 70% */
        }

        .card {
            background-color: white;
            padding: 20px;
            border: 1px solid #ccc;
            box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
            /* Default width for desktop */
            flex: 0 0 calc(33% - 20px); /* Roughly 3 cards per row with spacing */
        }

        
        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 1em 0;
            position: sticky; /* Example of sticky footer */
            bottom: 0;
            width: 100%;
        }

        /* Media Queries */

        /* Tablet View (min-width: 768px and max-width: 1024px) */
        @media (min-width: 768px) and (max-width: 1024px) {
            .container {
                flex-direction: row; 
            }

            .sidebar {
                flex: 0 0 30%;
            }

            .main-content {
                flex: 1 0 65%;
            }

            .card {
                flex: 0 0 calc(50% - 20px); /* 2 cards per row on tablet */
            }
        }

        /* Mobile View (max-width: 767px) */
        @media (max-width: 767px) {
            nav ul {
                flex-direction: column;
                align-items: flex-start;
                margin-top: 1em;
            }

            nav ul li {
                margin-left: 0;
                margin-bottom: 0.5em;
            }

            .container {
                flex-direction: column; /* Stack sidebar and main content */
            }

            .sidebar {
                flex: 0 0 auto; /* Take up full width */
                margin-bottom: 20px;
            }

            .main-content {
                flex: 0 0 auto; /* Take up full width */
            }

            .card {
                flex: 0 0 100%; /* One card per row on mobile */
            }
        }
    </style>
</head>
<body>

    <nav>
        <div class="logo">My Website</div>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Services</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>

    <div class="container">
        <aside class="sidebar">
            <h2>Sidebar</h2>
            <p>This is the sidebar content. It can contain navigation, ads, or other information.</p>
        </aside>

        <main class="main-content">
            <h1>Main Content</h1>
            <p>This is the main content area of the webpage. It can contain articles, blog posts, or other primary information.</p>

            <div class="card">
                <h3>Card 1</h3>
                <p>Content for card 1.</p>
            </div>
            <div class="card">
                <h3>Card 2</h3>
                <p>Content for card 2.</p>
            </div>
            <div class="card">
                <h3>Card 3</h3>
                <p>Content for card 3.</p>
            </div>
            <div class="card">
                <h3>Card 4</h3>
                <p>Content for card 4.</p>
            </div>
            <div class="card">
                <h3>Card 5</h3>
                <p>Content for card 5.</p>
            </div>
            <div class="card">
                <h3>Card 6</h3>
                <p>Content for card 6.</p>
            </div>
        </main>
    </div>

    <footer>
        <p>&copy; 2023 My Awesome Website</p>
    </footer>

</body>
</html>
