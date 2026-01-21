# UPI-payment-app-
web devolopment using html, css ,js code
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>UPI Pay</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Poppins', sans-serif;
    }

    body {
        height: 100vh;
        background: linear-gradient(135deg, #667eea, #764ba2);
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .card {
        width: 350px;
        padding: 25px;
        border-radius: 20px;
        background: rgba(255,255,255,0.15);
        backdrop-filter: blur(15px);
        box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        color: white;
        text-align: center;
    }

    .logo {
        font-size: 28px;
        font-weight: 700;
        margin-bottom: 10px;
    }

    .logo span {
        color: #ffd86f;
    }

    input {
        width: 100%;
        padding: 12px;
        margin: 10px 0;
        border-radius: 10px;
        border: none;
        outline: none;
        font-size: 16px;
    }

    button {
        width: 100%;
        padding: 12px;
        margin-top: 15px;
        border-radius: 12px;
        border: none;
        font-size: 18px;
        font-weight: 600;
        color: white;
        background: linear-gradient(135deg, #ff512f, #dd2476);
        cursor: pointer;
        transition: 0.3s;
    }

    button:hover {
        transform: scale(1.05);
        box-shadow: 0 5px 20px rgba(0,0,0,0.3);
    }

    .success {
        margin-top: 15px;
        color: #aaffaa;
        font-weight: 500;
        display: none;
    }

    .apps {
        display: flex;
        justify-content: space-around;
        margin-top: 15px;
    }

    .app {
        width: 45px;
        height: 45px;
        border-radius: 50%;
        background: white;
        color: #333;
        display: flex;
        align-items: center;
        justify-content: center;
        font-weight: bold;
        cursor: pointer;
        transition: 0.3s;
    }

    .app:hover {
        transform: scale(1.2);
        background: #ffd86f;
    }
</style>
</head>

<body>

<div class="card">
    <div class="logo">UPI<span>Pay</span></div>
    <p>Fast • Secure • Digital</p>

    <input type="text" id="upi" placeholder="Enter UPI ID (name@bank)">
    <input type="number" id="amount" placeholder="Enter Amount (₹)">

    <button onclick="pay()">Pay Now</button>

    <div class="apps">
        <div class="app">G</div>
        <div class="app">P</div>
        <div class="app">A</div>
    </div>

    <div class="success" id="successMsg">
        ✅ Payment Successful!
    </div>
</div>

<script>
function pay() {
    const upi = document.getElementById("upi").value;
    const amount = document.getElementById("amount").value;
    const success = document.getElementById("successMsg");

    if (!upi.includes("@") || amount <= 0) {
        alert("Please enter valid UPI ID and amount");
        return;
    }

    success.style.display = "block";
    success.innerHTML = `✅ ₹${amount} sent to ${upi}`;
}
</script>

</body>
</html>

