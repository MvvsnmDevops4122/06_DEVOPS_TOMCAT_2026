# 📁 Apache HTTPD Server (Web Server)

Step-by-Step Setup:

# Step 1: Check if the service is running:

systemctl status httpd

# Step 2: Install HTTPD if not installed:

yum install httpd -y

# Step 3: Start the web server:

service httpd start

# or

systemctl start httpd

📝 Note: Default port is 80

Access via: http://65.0.182.70

# Step 4: Make sure port 80 is allowed in EC2 security group inbound rules.

# Step 5: 📁 Default web root directory:

/var/www/html/index.html

# Add below html code:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CarePlus Hospital</title>
  <style>
    body { margin: 0; font-family: Arial, sans-serif; background: #0f172a; color: #e2e8f0; }
    header { display: flex; justify-content: space-between; align-items: center; background: #1e293b; padding: 15px 40px; }
    header h1 { color: #38bdf8; margin: 0; }
    nav a { color: #e2e8f0; text-decoration: none; margin: 0 15px; }
    nav a:hover { color: #38bdf8; }
    .hero { text-align: center; padding: 80px 20px; background: linear-gradient(145deg, #0f172a, #1e293b); }
    .hero h2 { font-size: 2.5rem; margin-bottom: 20px; color: #fff; }
    footer { background: #1e293b; color: #cbd5e1; text-align: center; padding: 20px; margin-top: 30px; }
  </style>
</head>
<body>
  <header>
    <h1>CarePlus Hospital</h1>
    <nav>
      <a href="#departments">Departments</a>
      <a href="#doctors">Doctors</a>
      <a href="#appointment">Appointment</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>
  <section class="hero">
    <h2>Compassionate care, advanced medicine.</h2>
    <p>Multispeciality hospital with modern facilities.</p>
    <button>Book Appointment</button>
  </section>
  <footer>
    <p>&copy; 2025 CarePlus Hospital | All Rights Reserved</p>
  </footer>
</body>
</html>
```

# 🛠️ Apache config directory:

/etc/httpd/conf
