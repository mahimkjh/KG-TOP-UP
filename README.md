<!DOCTYPE html><html lang="en"><head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KG TOP UP</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
    <style>
        body {
            background-color: #0d1117;
            color: #fff;
            font-family: Arial, sans-serif;
        }header {
        text-align: center;
        padding: 20px;
        background-color: #161b22;
    }

    .logo {
        max-height: 100px;
    }

    .section {
        padding: 20px;
    }

    .topup-card {
        background-color: #1c1f26;
        padding: 20px;
        border-radius: 10px;
        margin-bottom: 20px;
    }

    .footer {
        background-color: #161b22;
        text-align: center;
        padding: 20px;
        margin-top: 20px;
        border-top: 1px solid #333;
    }

    .form-control, .btn {
        margin-top: 10px;
    }
</style>

</head><body>
<header>
    <img src="logo.png" alt="KG Logo" class="logo">
    <h1>KG TOP UP</h1>
</header><div class="section container">
    <h3 class="mb-4">Free Fire Diamond Top-Up</h3><form id="topupForm">
    <label for="ffid" class="form-label">Free Fire UID:</label>
    <input type="text" class="form-control" id="ffid" placeholder="Enter your UID" required>

    <label for="package" class="form-label">Select Diamond Package:</label>
    <select class="form-control" id="package" required>
        <option value="100 Diamonds - ৳85">100 Diamonds - ৳85</option>
        <option value="200 Diamonds - ৳170">200 Diamonds - ৳170</option>
        <option value="Weekly Member - ৳160">Weekly Member - ৳160</option>
    </select>

    <div id="paymentInfo" class="mt-4 d-none">
        <h5>Step 1: Make payment</h5>
        <p>Send money to any of the numbers below:</p>
        <ul>
            <li><strong>Bkash:</strong> 01918881047</li>
            <li><strong>Nagad:</strong> 01782455456</li>
        </ul>
        <label for="trxid" class="form-label">Step 2: Enter your Transaction ID:</label>
        <input type="text" class="form-control" id="trxid" placeholder="Your TrxID" required>
    </div>

    <button type="button" class="btn btn-warning w-100" onclick="showPaymentBox()">Buy Now</button>
    <button type="submit" class="btn btn-success w-100 d-none mt-2" id="submitBtn">Submit Order</button>
</form>

<div id="transactionMessage" class="alert alert-info mt-4 d-none"></div>

</div><div class="section container">
    <h4>Payment Support</h4>
    <p><strong>WhatsApp:</strong> 01830335520</p>
</div><div class="footer">
    <p>&copy; 2025 KG TOP UP. All Rights Reserved.</p>
</div><script>
    function showPaymentBox() {
        document.getElementById('paymentInfo').classList.remove('d-none');
        document.getElementById('submitBtn').classList.remove('d-none');
    }

    document.getElementById('topupForm').addEventListener('submit', function (e) {
        e.preventDefault();
        const uid = document.getElementById('ffid').value;
        const pack = document.getElementById('package').value;
        const trx = document.getElementById('trxid').value;

        const message = document.getElementById('transactionMessage');
        message.classList.remove('d-none');
        message.innerHTML = `✅ <strong>Order Received!</strong><br>UID: <strong>${uid}</strong><br>Package: <strong>${pack}</strong><br>Transaction ID: <strong>${trx}</strong><br><br>We will process your order shortly.`;

        document.getElementById('topupForm').reset();
        document.getElementById('paymentInfo').classList.add('d-none');
        document.getElementById('submitBtn').classList.add('d-none');
    });
</script></body>
</html>
