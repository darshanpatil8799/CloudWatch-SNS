<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Linux EC2 with PuTTY | Darshan Patil</title>

    <meta name="description"
          content="Linux Server on AWS EC2 with PuTTY and SSH - Darshan Patil">

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: #0b1120;
            color: #e5e7eb;
            line-height: 1.7;
        }

        /* NAVBAR */
        nav {
            position: sticky;
            top: 0;
            z-index: 1000;
            background: rgba(11, 17, 32, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid #26324a;
        }

        .nav-container {
            max-width: 1150px;
            margin: auto;
            padding: 18px 25px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 22px;
            font-weight: bold;
            color: #38bdf8;
        }

        nav a {
            color: #cbd5e1;
            text-decoration: none;
            margin-left: 22px;
            font-size: 14px;
        }

        nav a:hover {
            color: #38bdf8;
        }

        /* HERO */
        .hero {
            min-height: 90vh;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 50px 20px;
            background:
                radial-gradient(circle at top right, #123d63, transparent 35%),
                radial-gradient(circle at bottom left, #172554, transparent 35%);
        }

        .hero-content {
            max-width: 900px;
        }

        .badge {
            display: inline-block;
            padding: 8px 18px;
            border: 1px solid #38bdf8;
            border-radius: 30px;
            color: #38bdf8;
            margin-bottom: 20px;
            font-size: 14px;
        }

        h1 {
            font-size: clamp(42px, 7vw, 75px);
            line-height: 1.1;
            margin-bottom: 20px;
        }

        .gradient {
            background: linear-gradient(90deg, #38bdf8, #818cf8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            max-width: 700px;
            margin: auto;
            color: #94a3b8;
            font-size: 18px;
        }

        .buttons {
            margin-top: 30px;
        }

        .btn {
            display: inline-block;
            padding: 13px 24px;
            border-radius: 8px;
            text-decoration: none;
            margin: 7px;
            font-weight: bold;
            transition: 0.3s;
        }

        .primary {
            background: #38bdf8;
            color: #07111f;
        }

        .secondary {
            border: 1px solid #475569;
            color: white;
        }

        .btn:hover {
            transform: translateY(-3px);
        }

        /* COMMON */
        section {
            max-width: 1150px;
            margin: auto;
            padding: 80px 25px;
        }

        .section-title {
            text-align: center;
            margin-bottom: 45px;
        }

        .section-title h2 {
            font-size: 36px;
            margin-bottom: 10px;
        }

        .section-title p {
            color: #94a3b8;
        }

        /* CARDS */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 20px;
        }

        .card {
            background: #111827;
            border: 1px solid #26324a;
            border-radius: 14px;
            padding: 28px;
            transition: 0.3s;
        }

        .card:hover {
            transform: translateY(-6px);
            border-color: #38bdf8;
            box-shadow: 0 10px 35px rgba(0,0,0,0.3);
        }

        .icon {
            font-size: 35px;
            margin-bottom: 15px;
        }

        .card h3 {
            margin-bottom: 10px;
            color: #f8fafc;
        }

        .card p {
            color: #94a3b8;
            font-size: 15px;
        }

        /* REQUIREMENTS */
        .requirements {
            background: #0f172a;
            border-top: 1px solid #1e293b;
            border-bottom: 1px solid #1e293b;
        }

        .requirement-list {
            max-width: 850px;
            margin: auto;
        }

        .requirement {
            display: flex;
            gap: 18px;
            padding: 20px;
            margin-bottom: 12px;
            background: #111827;
            border-radius: 10px;
            border: 1px solid #26324a;
        }

        .requirement span {
            font-size: 24px;
        }

        /* STEPS */
        .steps {
            max-width: 850px;
            margin: auto;
        }

        .step {
            display: flex;
            gap: 20px;
            margin-bottom: 25px;
            padding: 25px;
            background: #111827;
            border: 1px solid #26324a;
            border-radius: 12px;
        }

        .number {
            min-width: 42px;
            height: 42px;
            border-radius: 50%;
            background: #38bdf8;
            color: #07111f;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        .step h3 {
            margin-bottom: 5px;
        }

        .step p {
            color: #94a3b8;
        }

        /* FLOW */
        .flow {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 15px;
            flex-wrap: wrap;
        }

        .flow-box {
            padding: 20px 25px;
            border-radius: 10px;
            background: #111827;
            border: 1px solid #38bdf8;
            text-align: center;
        }

        .arrow {
            font-size: 25px;
            color: #38bdf8;
        }

        /* TECHNOLOGIES */
        .tech {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 12px;
        }

        .tech span {
            padding: 10px 18px;
            background: #111827;
            border: 1px solid #334155;
            border-radius: 25px;
            color: #cbd5e1;
        }

        /* FOOTER */
        footer {
            text-align: center;
            padding: 45px 20px;
            border-top: 1px solid #26324a;
            color: #94a3b8;
        }

        footer strong {
            color: #38bdf8;
        }

        @media (max-width: 700px) {
            nav a {
                display: none;
            }

            .hero {
                min-height: 80vh;
            }

            .step {
                flex-direction: column;
            }
        }
    </style>
</head>

<body>

<!-- NAVIGATION -->
<nav>
    <div class="nav-container">
        <div class="logo">☁️ Darshan Patil</div>

        <div>
            <a href="#about">About</a>
            <a href="#requirements">Requirements</a>
            <a href="#steps">Steps</a>
            <a href="#technologies">Technologies</a>
        </div>
    </div>
</nav>


<!-- HERO -->
<header class="hero">
    <div class="hero-content">

        <div class="badge">AWS • Linux • SSH • PuTTY</div>

        <h1>
            Linux Server<br>
            <span class="gradient">with PuTTY</span>
        </h1>

        <p>
            A hands-on AWS EC2 project demonstrating how to launch a
            Linux server and securely connect to it using PuTTY and SSH.
        </p>

        <div class="buttons">
            <a href="#steps" class="btn primary">
                🚀 Explore Project
            </a>

            <a href="#technologies" class="btn secondary">
                🛠️ Technologies
            </a>
        </div>

    </div>
</header>


<!-- ABOUT -->
<section id="about">

    <div class="section-title">
        <h2>📌 Project Overview</h2>
        <p>Learning AWS Cloud & Linux through hands-on practice</p>
    </div>

    <div class="grid">

        <div class="card">
            <div class="icon">☁️</div>
            <h3>AWS EC2</h3>
            <p>
                Launch and configure a Linux server using
                Amazon EC2.
            </p>
        </div>

        <div class="card">
            <div class="icon">🐧</div>
            <h3>Linux</h3>
            <p>
                Learn basic Linux server administration
                through the command line.
            </p>
        </div>

        <div class="card">
            <div class="icon">🔐</div>
            <h3>SSH</h3>
            <p>
                Establish secure remote access to the
                Linux server.
            </p>
        </div>

        <div class="card">
            <div class="icon">💻</div>
            <h3>PuTTY</h3>
            <p>
                Use PuTTY from Windows to remotely
                manage the Linux EC2 server.
            </p>
        </div>

    </div>

</section>


<!-- REQUIREMENTS -->
<div class="requirements" id="requirements">

<section>

    <div class="section-title">
        <h2>🔑 Requirements</h2>
        <p>Things required before starting the project</p>
    </div>

    <div class="requirement-list">

        <div class="requirement">
            <span>☁️</span>
            <div>
                <strong>AWS Account</strong>
                <p>
                    An active AWS account with permission
                    to launch EC2 instances.
                </p>
            </div>
        </div>

        <div class="requirement">
            <span>💻</span>
            <div>
                <strong>PuTTY & PuTTYgen</strong>
                <p>
                    Install PuTTY and PuTTYgen on your
                    Windows machine.
                </p>
            </div>
        </div>

        <div class="requirement">
            <span>🌐</span>
            <div>
                <strong>Internet Connection</strong>
                <p>
                    Stable internet access for AWS Console
                    and SSH connectivity.
                </p>
            </div>
        </div>

        <div class="requirement">
            <span>🔑</span>
            <div>
                <strong>AWS Key Pair</strong>
                <p>
                    Download the private .pem key generated
                    while creating the EC2 instance.
                </p>
            </div>
        </div>

        <div class="requirement">
            <span>🛡️</span>
            <div>
                <strong>Security Group</strong>
                <p>
                    Allow SSH traffic on Port 22 from your
                    trusted IP address.
                </p>
            </div>
        </div>

    </div>

</section>

</div>


<!-- CONNECTION FLOW -->
<section>

    <div class="section-title">
        <h2>🔗 Connection Architecture</h2>
        <p>How the connection works</p>
    </div>

    <div class="flow">

        <div class="flow-box">
            👨‍💻<br>
            <strong>Windows PC</strong>
        </div>

        <div class="arrow">→</div>

        <div class="flow-box">
            🔑<br>
            <strong>PuTTY / .PPK</strong>
        </div>

        <div class="arrow">→</div>

        <div class="flow-box">
            🌐<br>
            <strong>Internet</strong>
        </div>

        <div class="arrow">→</div>

        <div class="flow-box">
            ☁️<br>
            <strong>AWS EC2</strong>
        </div>

        <div class="arrow">→</div>

        <div class="flow-box">
            🐧<br>
            <strong>Linux Server</strong>
        </div>

    </div>

</section>


<!-- STEPS -->
<section id="steps">

    <div class="section-title">
        <h2>🚀 Project Steps</h2>
        <p>Complete workflow from EC2 creation to Linux login</p>
    </div>

    <div class="steps">

        <div class="step">
            <div class="number">1</div>
            <div>
                <h3>Launch EC2 Instance</h3>
                <p>
                    Open AWS Management Console and navigate
                    to the EC2 Dashboard.
                </p>
            </div>
        </div>

        <div class="step">
            <div class="number">2</div>
            <div>
                <h3>Choose Linux AMI</h3>
                <p>
                    Select an appropriate Linux AMI such as
                    Amazon Linux or Ubuntu.
                </p>
            </div>
        </div>

        <div class="step">
            <div class="number">3</div>
            <div>
                <h3>Select Instance Type</h3>
                <p>
                    Select a suitable EC2 instance type
                    according to your requirements.
                </p>
            </div>
        </div>

        <div class="step">
            <div class="number">4</div>
            <div>
                <h3>Create Key Pair</h3>
                <p>
                    Create and download an AWS key pair
                    in .pem format.
                </p>
            </div>
        </div>

        <div class="step">
            <div class="number">5</div>
            <div>
                <h3>Configure Security Group</h3>
                <p>
                    Allow SSH traffic through Port 22
                    from your trusted IP address.
                </p>
            </div>
        </div>

        <div class="step">
            <div class="number">6</div>
            <div>
                <h3>Convert PEM to PPK</h3>
                <p>
                    Open PuTTYgen, load the AWS .pem file
                    and save it as a .ppk file.
                </p>
            </div>
        </div>

        <div class="step">
            <div class="number">7</div>
            <div>
                <h3>Configure PuTTY</h3>
                <p>
                    Enter the EC2 Public IP/DNS and configure
                    the generated .ppk private key.
                </p>
            </div>
        </div>

        <div class="step">
            <div class="number">8</div>
            <div>
                <h3>Connect to Linux</h3>
                <p>
                    Click Open and log in using the default
                    Linux username.
                </p>
            </div>
        </div>

    </div>

</section>


<!-- LOGIN -->
<section>

    <div class="section-title">
        <h2>🔐 Linux Login</h2>
        <p>Default usernames depend on the selected AMI</p>
    </div>

    <div class="grid">

        <div class="card">
            <div class="icon">🐧</div>
            <h3>Amazon Linux</h3>
            <p>Username: <strong>ec2-user</strong></p>
        </div>

        <div class="card">
            <div class="icon">🟠</div>
            <h3>Ubuntu</h3>
            <p>Username: <strong>ubuntu</strong></p>
        </div>

        <div class="card">
            <div class="icon">🔴</div>
            <h3>CentOS</h3>
            <p>Username: <strong>centos</strong></p>
        </div>

    </div>

</section>


<!-- TECHNOLOGIES -->
<section id="technologies">

    <div class="section-title">
        <h2>🛠️ Technologies & Tools</h2>
        <p>Tools used in this hands-on project</p>
    </div>

    <div class="tech">

        <span>☁️ AWS</span>
        <span>🖥️ Amazon EC2</span>
        <span>🐧 Linux</span>
        <span>💻 PuTTY</span>
        <span>🔑 PuTTYgen</span>
        <span>🔐 SSH</span>
        <span>🌐 Security Groups</span>
        <span>🔑 Key Pair</span>

    </div>

</section>


<!-- LEARNING -->
<section>

    <div class="section-title">
        <h2>🎯 Learning Outcomes</h2>
        <p>Skills developed through this project</p>
    </div>

    <div class="grid">

        <div class="card">
            <h3>☁️ Cloud Computing</h3>
            <p>
                Practical understanding of launching and
                accessing AWS EC2 infrastructure.
            </p>
        </div>

        <div class="card">
            <h3>🐧 Linux Administration</h3>
            <p>
                Hands-on experience working with a remote
                Linux server through CLI.
            </p>
        </div>

        <div class="card">
            <h3>🔐 Secure Access</h3>
            <p>
                Understanding SSH authentication,
                key pairs and security groups.
            </p>
        </div>

        <div class="card">
            <h3>🚀 DevOps Foundation</h3>
            <p>
                Builds foundational skills required for
                Cloud Engineering and DevOps.
            </p>
        </div>

    </div>

</section>


<!-- FOOTER -->
<footer>

    <p>
        🚀 <strong>Linux Server with PuTTY</strong>
    </p>

    <p>
        AWS EC2 • Linux • SSH • PuTTY
    </p>

    <br>

    <p>
        Created by <strong>Darshan Patil</strong>
    </p>

    <p>
        © 2026 Darshan Patil. All Rights Reserved.
    </p>

</footer>

</body>
</html>
