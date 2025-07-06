
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة تحويل العملات الرقمية - USDT</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            direction: rtl;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 30px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .header h1 {
            color: #2d3748;
            font-size: 2.5rem;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .header p {
            color: #718096;
            font-size: 1.1rem;
        }

        .exchange-rate {
            background: linear-gradient(45deg, #4299e1, #3182ce);
            color: white;
            padding: 15px 25px;
            border-radius: 50px;
            display: inline-block;
            margin-top: 20px;
            font-weight: 600;
            box-shadow: 0 10px 25px rgba(66, 153, 225, 0.3);
        }

        .main-card {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            margin-bottom: 30px;
        }

        .progress-steps {
            display: flex;
            justify-content: space-between;
            margin-bottom: 40px;
            position: relative;
        }

        .progress-steps::before {
            content: '';
            position: absolute;
            top: 20px;
            left: 0;
            right: 0;
            height: 4px;
            background: #e2e8f0;
            z-index: 1;
        }

        .progress-line {
            position: absolute;
            top: 20px;
            left: 0;
            height: 4px;
            background: linear-gradient(45deg, #4299e1, #3182ce);
            z-index: 2;
            transition: width 0.5s ease;
        }

        .step {
            background: #e2e8f0;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 600;
            color: #718096;
            position: relative;
            z-index: 3;
            transition: all 0.3s ease;
        }

        .step.active {
            background: linear-gradient(45deg, #4299e1, #3182ce);
            color: white;
            transform: scale(1.1);
            box-shadow: 0 5px 15px rgba(66, 153, 225, 0.4);
        }

        .step.completed {
            background: #48bb78;
            color: white;
        }

        .step-labels {
            display: flex;
            justify-content: space-between;
            margin-top: 10px;
            font-size: 0.9rem;
            color: #718096;
        }

        .form-section {
            margin-bottom: 30px;
        }

        .form-section h2 {
            color: #2d3748;
            font-size: 1.8rem;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .form-section p {
            color: #718096;
            margin-bottom: 25px;
        }

        .form-group {
            margin-bottom: 25px;
        }

        .form-group label {
            display: block;
            color: #4a5568;
            font-weight: 600;
            margin-bottom: 8px;
            font-size: 0.95rem;
        }

        .form-group label i {
            margin-left: 8px;
            color: #4299e1;
        }

        .form-control {
            width: 100%;
            padding: 15px 20px;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            font-size: 1rem;
            transition: all 0.3s ease;
            background: #f7fafc;
        }

        .form-control:focus {
            outline: none;
            border-color: #4299e1;
            background: white;
            box-shadow: 0 0 0 3px rgba(66, 153, 225, 0.1);
        }

        .transaction-types {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-top: 15px;
        }

        .transaction-type {
            padding: 25px;
            border: 2px solid #e2e8f0;
            border-radius: 15px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            background: #f7fafc;
        }

        .transaction-type:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }

        .transaction-type.selected {
            border-color: #4299e1;
            background: linear-gradient(135deg, #ebf8ff, #bee3f8);
            transform: translateY(-2px);
        }

        .transaction-type.buy.selected {
            border-color: #48bb78;
            background: linear-gradient(135deg, #f0fff4, #c6f6d5);
        }

        .transaction-type.sell.selected {
            border-color: #ed8936;
            background: linear-gradient(135deg, #fffaf0, #fbd38d);
        }

        .transaction-type i {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: #4299e1;
        }

        .transaction-type.buy i {
            color: #48bb78;
        }

        .transaction-type.sell i {
            color: #ed8936;
        }

        .transaction-type h3 {
            color: #2d3748;
            font-weight: 600;
            font-size: 1.1rem;
        }

        .network-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 15px;
        }

        .network-option {
            padding: 20px;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            background: #f7fafc;
        }

        .network-option:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }

        .network-option.selected {
            border-color: #4299e1;
            background: linear-gradient(135deg, #ebf8ff, #bee3f8);
        }

        .network-option .network-name {
            font-weight: 600;
            color: #2d3748;
            margin-bottom: 5px;
            text-transform: uppercase;
        }

        .network-option .network-fee {
            font-size: 0.9rem;
            color: #718096;
        }

        .payment-methods {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            margin-top: 15px;
        }

        .payment-method {
            padding: 20px;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            background: #f7fafc;
        }

        .payment-method:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }

        .payment-method.selected {
            border-color: #4299e1;
            background: linear-gradient(135deg, #ebf8ff, #bee3f8);
        }

        .payment-method h4 {
            color: #2d3748;
            font-weight: 600;
            margin-bottom: 5px;
        }

        .info-card {
            background: linear-gradient(135deg, #ebf8ff, #bee3f8);
            border: 1px solid #4299e1;
            border-radius: 15px;
            padding: 25px;
            margin: 20px 0;
        }

        .info-card.warning {
            background: linear-gradient(135deg, #fffbeb, #fed7aa);
            border-color: #f6ad55;
        }

        .info-card.success {
            background: linear-gradient(135deg, #f0fff4, #c6f6d5);
            border-color: #48bb78;
        }

        .info-card.error {
            background: linear-gradient(135deg, #fed7d7, #feb2b2);
            border-color: #f56565;
        }

        .info-card h3 {
            color: #2d3748;
            font-weight: 600;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
        }

        .info-card h3 i {
            margin-left: 10px;
            font-size: 1.2rem;
        }

        .address-display {
            background: white;
            padding: 20px;
            border-radius: 10px;
            border: 1px solid #e2e8f0;
            margin-top: 15px;
            position: relative;
        }

        .address-display .address-text {
            font-family: 'Courier New', monospace;
            word-break: break-all;
            color: #2d3748;
            font-size: 0.95rem;
            line-height: 1.5;
        }

        .copy-btn {
            position: absolute;
            top: 15px;
            left: 15px;
            background: #4299e1;
            color: white;
            border: none;
            padding: 8px 12px;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.9rem;
        }

        .copy-btn:hover {
            background: #3182ce;
            transform: translateY(-1px);
        }

        .copy-btn.copied {
            background: #48bb78;
        }

        .summary-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 25px 0;
        }

        .summary-card {
            background: #f7fafc;
            padding: 25px;
            border-radius: 15px;
            border: 1px solid #e2e8f0;
        }

        .summary-card h3 {
            color: #2d3748;
            font-weight: 600;
            margin-bottom: 15px;
            font-size: 1.1rem;
        }

        .summary-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            padding-bottom: 8px;
            border-bottom: 1px solid #e2e8f0;
        }

        .summary-item:last-child {
            border-bottom: none;
            font-weight: 600;
            color: #2d3748;
            font-size: 1.05rem;
        }

        .btn {
            padding: 15px 30px;
            border: none;
            border-radius: 12px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
        }

        .btn i {
            margin-left: 8px;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
        }

        .btn:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .btn-primary {
            background: linear-gradient(45deg, #4299e1, #3182ce);
            color: white;
        }

        .btn-secondary {
            background: #e2e8f0;
            color: #4a5568;
        }

        .btn-success {
            background: linear-gradient(45deg, #48bb78, #38a169);
            color: white;
        }

        .btn-group {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
            gap: 15px;
        }

        .success-animation {
            text-align: center;
            padding: 40px;
        }

        .success-icon {
            font-size: 4rem;
            color: #48bb78;
            margin-bottom: 20px;
            animation: bounce 1s ease-in-out;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0);
            }
            40% {
                transform: translateY(-10px);
            }
            60% {
                transform: translateY(-5px);
            }
        }

        .loading-spinner {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s ease-in-out infinite;
            margin-left: 10px;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .hidden {
            display: none;
        }

        .fade-in {
            animation: fadeIn 0.5s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @media (max-width: 480px) {
            .container {
                padding: 15px;
            }

            .header h1 {
                font-size: 2rem;
            }

            .main-card {
                padding: 25px;
            }

            .transaction-types {
                grid-template-columns: 1fr;
            }

            .network-grid {
                grid-template-columns: 1fr;
            }

            .payment-methods {
                grid-template-columns: 1fr;
            }

            .summary-grid {
                grid-template-columns: 1fr;
            }

            .btn-group {
                flex-direction: column;
            }

            .progress-steps {
                flex-wrap: wrap;
                gap: 10px;
            }

            .step-labels {
                flex-wrap: wrap;
                gap: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1><i class="fas fa-exchange-alt"></i> منصة تحويل العملات الرقمية</h1>
            <p>تحويل آمن وسريع لعملة USDT</p>
            <div class="exchange-rate">
                <i class="fas fa-dollar-sign"></i>
                سعر الصرف: 1 USD = 12000 ل.س
            </div>
        </div>

        <!-- Main Card -->
        <div class="main-card">
            <!-- Progress Steps -->
            <div class="progress-steps">
                <div class="progress-line" id="progressLine"></div>
                <div class="step active" id="step1">1</div>
                <div class="step" id="step2">2</div>
                <div class="step" id="step3">3</div>
                <div class="step" id="step4">4</div>
            </div>
            <div class="step-labels">
                <span>المعلومات الشخصية</span>
                <span>نوع العملية</span>
                <span>تفاصيل التحويل</span>
                <span>التأكيد</span>
            </div>

            <!-- Step 1: Personal Information -->
            <div id="stepContent1" class="step-content fade-in">
                <div class="form-section">
                    <h2>المعلومات الشخصية</h2>
                    <p>يرجى إدخال معلوماتك الشخصية للمتابعة</p>

                    <div class="form-group">
                        <label for="fullName"><i class="fas fa-user"></i>الاسم الثلاثي</label>
                        <input type="text" id="fullName" class="form-control" placeholder="أدخل اسمك الثلاثي">
                    </div>

                    <div class="form-group">
                        <label for="phoneNumber"><i class="fas fa-phone"></i>رقم الهاتف</label>
                        <input type="tel" id="phoneNumber" class="form-control" placeholder="أدخل رقم هاتفك">
                    </div>

                    <div class="form-group">
                        <label for="city"><i class="fas fa-map-marker-alt"></i>المدينة</label>
                        <input type="text" id="city" class="form-control" placeholder="أدخل مدينتك">
                    </div>

                    <div class="form-group">
                        <label>نوع العملية</label>
                        <div class="transaction-types">
                            <div class="transaction-type buy" data-type="buy">
                                <i class="fas fa-wallet"></i>
                                <h3>شراء USDT</h3>
                            </div>
                            <div class="transaction-type sell" data-type="sell">
                                <i class="fas fa-paper-plane"></i>
                                <h3>بيع USDT</h3>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="btn-group">
                    <div></div>
                    <button class="btn btn-primary" onclick="nextStep()" id="nextBtn1" disabled>
                        التالي <i class="fas fa-arrow-left"></i>
                    </button>
                </div>
            </div>

            <!-- Step 2: Transaction Details -->
            <div id="stepContent2" class="step-content hidden">
                <!-- Buy Form -->
                <div id="buyForm" class="form-section hidden">
                    <h2>شراء USDT</h2>
                    <p>أدخل تفاصيل عملية الشراء</p>

                    <div class="form-group">
                        <label for="buyAmount">الكمية المطلوبة (USDT)</label>
                        <input type="number" id="buyAmount" class="form-control" placeholder="أدخل الكمية" min="1">
                        <div id="buyFeeInfo" class="info-card hidden">
                            <h3><i class="fas fa-info-circle"></i>معلومات العمولة</h3>
                            <p id="buyFeeText"></p>
                        </div>
                    </div>

                    <div class="form-group">
                        <label>اختر الشبكة</label>
                        <div class="network-grid">
                            <div class="network-option" data-network="trc20" data-fee="2">
                                <div class="network-name">TRC20</div>
                                <div class="network-fee">رسوم الشبكة: $2</div>
                            </div>
                            <div class="network-option" data-network="bep20" data-fee="0.15">
                                <div class="network-name">BEP20</div>
                                <div class="network-fee">رسوم الشبكة: $0.15</div>
                            </div>
                            <div class="network-option" data-network="erc20" data-fee="0.3">
                                <div class="network-name">ERC20</div>
                                <div class="network-fee">رسوم الشبكة: $0.3</div>
                            </div>
                            <div class="network-option" data-network="binancepay" data-fee="0">
                                <div class="network-name">Binance Pay</div>
                                <div class="network-fee">رسوم الشبكة: $0</div>
                            </div>
                        </div>
                    </div>

                    <div class="form-group">
                        <label for="walletAddress">عنوان المحفظة</label>
                        <input type="text" id="walletAddress" class="form-control" placeholder="أدخل عنوان محفظتك">
                    </div>

                    <div class="form-group">
                        <label>طريقة الدفع</label>
                        <div class="payment-methods">
                            <div class="payment-method" data-method="syriatelcash">
                                <h4>سيريتل كاش</h4>
                            </div>
                            <div class="payment-method" data-method="alharam">
                                <h4>حوالة الهرم</h4>
                            </div>
                            <div class="payment-method" data-method="bemo">
                                <h4>بنك بيمو</h4>
                            </div>
                            <div class="payment-method" data-method="shamcash">
                                <h4>شام كاش</h4>
                            </div>
                        </div>
                    </div>

                    <div class="form-group">
                        <label for="buyNotes">ملاحظات</label>
                        <textarea id="buyNotes" class="form-control" rows="3" placeholder="أدخل أي ملاحظات إضافية"></textarea>
                    </div>
                </div>

                <!-- Sell Form -->
                <div id="sellForm" class="form-section hidden">
                    <h2>بيع USDT</h2>
                    <p>أدخل تفاصيل عملية البيع</p>

                    <div class="form-group">
                        <label for="sellAmount">الكمية المراد بيعها (USDT)</label>
                        <input type="number" id="sellAmount" class="form-control" placeholder="أدخل الكمية" min="1">
                        <div id="sellFeeInfo" class="info-card hidden">
                            <h3><i class="fas fa-info-circle"></i>معلومات العمولة</h3>
                            <p id="sellFeeText"></p>
                        </div>
                    </div>

                    <div class="form-group">
                        <label for="receivingMethod">طريقة الاستلام</label>
                        <select id="receivingMethod" class="form-control">
                            <option value="">اختر طريقة الاستلام</option>
                            <option value="syriatelcash">سيريتل كاش</option>
                            <option value="alharam">حوالة الهرم</option>
                            <option value="bemo">بنك بيمو</option>
                            <option value="shamcash">شام كاش</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="accountDetails">تفاصيل الحساب</label>
                        <input type="text" id="accountDetails" class="form-control" placeholder="أدخل تفاصيل حسابك">
                    </div>

                    <div class="form-group">
                        <label>اختر الشبكة لإرسال USDT</label>
                        <div class="network-grid">
                            <div class="network-option" data-network="trc20" data-fee="2">
                                <div class="network-name">TRC20</div>
                                <div class="network-fee">رسوم الشبكة: $2</div>
                            </div>
                            <div class="network-option" data-network="bep20" data-fee="0.15">
                                <div class="network-name">BEP20</div>
                                <div class="network-fee">رسوم الشبكة: $0.15</div>
                            </div>
                            <div class="network-option" data-network="erc20" data-fee="0.3">
                                <div class="network-name">ERC20</div>
                                <div class="network-fee">رسوم الشبكة: $0.3</div>
                            </div>
                            <div class="network-option" data-network="binancepay" data-fee="0">
                                <div class="network-name">Binance Pay</div>
                                <div class="network-fee">رسوم الشبكة: $0</div>
                            </div>
                        </div>
                    </div>

                    <div class="form-group">
                        <label for="sellNotes">ملاحظات</label>
                        <textarea id="sellNotes" class="form-control" rows="3" placeholder="أدخل أي ملاحظات إضافية"></textarea>
                    </div>
                </div>

                <div class="btn-group">
                    <button class="btn btn-secondary" onclick="prevStep()">
                        <i class="fas fa-arrow-right"></i> السابق
                    </button>
                    <button class="btn btn-primary" onclick="nextStep()" id="nextBtn2" disabled>
                        التالي <i class="fas fa-arrow-left"></i>
                    </button>
                </div>
            </div>

            <!-- Step 3: Payment/Transfer Details -->
            <div id="stepContent3" class="step-content hidden">
                <div class="form-section">
                    <h2 id="step3Title">تفاصيل الدفع</h2>
                    <p id="step3Description">استخدم التفاصيل التالية لإرسال الدفعة</p>

                    <div id="paymentDetails" class="info-card">
                        <h3><i class="fas fa-credit-card"></i>تفاصيل الدفع</h3>
                        <div class="address-display">
                            <div class="address-text" id="paymentAddress"></div>
                            <button class="copy-btn" onclick="copyToClipboard('paymentAddress')">
                                <i class="fas fa-copy"></i> نسخ
                            </button>
                        </div>
                    </div>

                    <div id="cryptoDetails" class="info-card hidden">
                        <h3><i class="fas fa-coins"></i>عنوان الإرسال</h3>
                        <div class="address-display">
                            <div class="address-text" id="cryptoAddress"></div>
                            <button class="copy-btn" onclick="copyToClipboard('cryptoAddress')">
                                <i class="fas fa-copy"></i> نسخ
                            </button>
                        </div>
                    </div>

                    <div class="info-card success">
                        <h3><i class="fas fa-calculator"></i>ملخص المبلغ</h3>
                        <div id="amountSummary"></div>
                    </div>
                </div>

                <div class="btn-group">
                    <button class="btn btn-secondary" onclick="prevStep()">
                        <i class="fas fa-arrow-right"></i> السابق
                    </button>
                    <button class="btn btn-primary" onclick="nextStep()">
                        تأكيد الطلب <i class="fas fa-check"></i>
                    </button>
                </div>
            </div>

            <!-- Step 4: Confirmation -->
            <div id="stepContent4" class="step-content hidden">
                <div class="form-section">
                    <h2>تأكيد الطلب</h2>
                    <p>راجع تفاصيل طلبك قبل الإرسال</p>

                    <div class="summary-grid">
                        <div class="summary-card">
                            <h3>المعلومات الشخصية</h3>
                            <div id="personalSummary"></div>
                        </div>
                        <div class="summary-card">
                            <h3>تفاصيل العملية</h3>
                            <div id="transactionSummary"></div>
                        </div>
                    </div>

                    <div class="info-card warning">
                        <h3><i class="fas fa-exclamation-triangle"></i>تنبيه مهم</h3>
                        <p id="warningText"></p>
                    </div>

                    <div id="errorMessage" class="info-card error hidden">
                        <h3><i class="fas fa-exclamation-circle"></i>خطأ</h3>
                        <p id="errorText"></p>
                    </div>
                </div>

                <div class="btn-group">
                    <button class="btn btn-secondary" onclick="prevStep()">
                        <i class="fas fa-arrow-right"></i> السابق
                    </button>
                    <button class="btn btn-success" onclick="submitOrder()" id="submitBtn">
                        <i class="fas fa-paper-plane"></i> إرسال الطلب
                    </button>
                </div>
            </div>

            <!-- Step 5: Success -->
            <div id="stepContent5" class="step-content hidden">
                <div class="success-animation">
                    <div class="success-icon">
                        <i class="fas fa-check-circle"></i>
                    </div>
                    <h2>تم إرسال الطلب بنجاح!</h2>
                    <p>تم إرسال طلبك عبر البريد الإلكتروني وسيتم التواصل معك قريباً لتأكيد العملية.</p>

                    <div class="info-card success">
                        <h3><i class="fas fa-receipt"></i>ملخص الطلب</h3>
                        <div id="finalSummary"></div>
                    </div>

                    <button class="btn btn-primary" onclick="resetForm()">
                        <i class="fas fa-plus"></i> طلب جديد
                    </button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Global variables
        let currentStep = 1;
        let formData = {
            personal: {},
            transaction: {},
            transactionType: ''
        };

        // Constants
        const EXCHANGE_RATE = 13000;
        const NETWORK_FEES = {
            trc20: 2,
            bep20: 0.15,
            erc20: 0.3,
            binancepay: 0
        };

        const PAYMENT_METHODS = {
            syriatelcash: {
                name: 'سيريتل كاش',
                address: '0934598967'
            },
            alharam: {
                name: 'حوالة الهرم',
                address: 'علي ابراهيم محمود\n0934598967\nاللاذقية'
            },
            bemo: {
                name: 'بنك بيمو',
                address: 'علي ابراهيم محمود\n060104947910013000000'
            },
            shamcash: {
                name: 'شام كاش',
                address: 'be456e0ea9392db4d68a7093ee317bc8\n5991161126028260'
            }
        };

        const CRYPTO_ADDRESSES = {
            bep20: '0x21802218d8d661d66F2C7959347a6382E1cc614F',
            trc20: 'TD2LoErPRkVPBxDk72ZErtiyi6agirZQjX',
            erc20: '0x21802218d8d661d66F2C7959347a6382E1cc614F',
            binancepay: '969755964'
        };

        // Initialize the application
        document.addEventListener('DOMContentLoaded', function() {
            setupEventListeners();
            updateProgressBar();
        });

        function setupEventListeners() {
            // Transaction type selection
            document.querySelectorAll('.transaction-type').forEach(type => {
                type.addEventListener('click', function() {
                    document.querySelectorAll('.transaction-type').forEach(t => t.classList.remove('selected'));
                    this.classList.add('selected');
                    formData.transactionType = this.dataset.type;
                    validateStep1();
                });
            });

            // Network selection
            document.querySelectorAll('.network-option').forEach(option => {
                option.addEventListener('click', function() {
                    const parent = this.closest('.network-grid');
                    parent.querySelectorAll('.network-option').forEach(o => o.classList.remove('selected'));
                    this.classList.add('selected');
                    
                    if (formData.transactionType === 'buy') {
                        formData.transaction.network = this.dataset.network;
                        formData.transaction.networkFee = parseFloat(this.dataset.fee);
                    } else {
                        formData.transaction.sellNetwork = this.dataset.network;
                        formData.transaction.sellNetworkFee = parseFloat(this.dataset.fee);
                    }
                    validateCurrentStep();
                });
            });

            // Payment method selection
            document.querySelectorAll('.payment-method').forEach(method => {
                method.addEventListener('click', function() {
                    document.querySelectorAll('.payment-method').forEach(m => m.classList.remove('selected'));
                    this.classList.add('selected');
                    formData.transaction.paymentMethod = this.dataset.method;
                    validateCurrentStep();
                });
            });

            // Form inputs
            document.getElementById('fullName').addEventListener('input', validateStep1);
            document.getElementById('phoneNumber').addEventListener('input', validateStep1);
            document.getElementById('city').addEventListener('input', validateStep1);
            
            document.getElementById('buyAmount').addEventListener('input', function() {
                updateFeeCalculation('buy');
                validateCurrentStep();
            });
            
            document.getElementById('sellAmount').addEventListener('input', function() {
                updateFeeCalculation('sell');
                validateCurrentStep();
            });
            
            document.getElementById('walletAddress').addEventListener('input', validateCurrentStep);
            document.getElementById('receivingMethod').addEventListener('change', validateCurrentStep);
            document.getElementById('accountDetails').addEventListener('input', validateCurrentStep);
        }

        function validateStep1() {
            const name = document.getElementById('fullName').value.trim();
            const phone = document.getElementById('phoneNumber').value.trim();
            const city = document.getElementById('city').value.trim();
            const transactionType = formData.transactionType;

            const isValid = name && phone && city && transactionType;
            document.getElementById('nextBtn1').disabled = !isValid;

            if (isValid) {
                formData.personal = { name, phone, city };
            }
        }

        function validateCurrentStep() {
            if (currentStep === 2) {
                validateStep2();
            }
        }

        function validateStep2() {
            let isValid = false;

            if (formData.transactionType === 'buy') {
                const amount = parseFloat(document.getElementById('buyAmount').value);
                const network = formData.transaction.network;
                const address = document.getElementById('walletAddress').value.trim();
                const paymentMethod = formData.transaction.paymentMethod;

                isValid = amount > 0 && network && address && paymentMethod;
                
                if (isValid) {
                    formData.transaction.amount = amount;
                    formData.transaction.address = address;
                    formData.transaction.notes = document.getElementById('buyNotes').value.trim();
                }
            } else {
                const amount = parseFloat(document.getElementById('sellAmount').value);
                const network = formData.transaction.sellNetwork;
                const receivingMethod = document.getElementById('receivingMethod').value;
                const accountDetails = document.getElementById('accountDetails').value.trim();

                isValid = amount > 0 && network && receivingMethod && accountDetails;
                
                if (isValid) {
                    formData.transaction.sellAmount = amount;
                    formData.transaction.receivingMethod = receivingMethod;
                    formData.transaction.accountDetails = accountDetails;
                    formData.transaction.sellNotes = document.getElementById('sellNotes').value.trim();
                }
            }

            document.getElementById('nextBtn2').disabled = !isValid;
        }

        function calculateFee(amount) {
            if (amount < 100) return 1.65;
            if (amount <= 5000) return amount * 0.0165;
            return amount * 0.0005;
        }

        function updateFeeCalculation(type) {
            const amountInput = document.getElementById(type + 'Amount');
            const feeInfo = document.getElementById(type + 'FeeInfo');
            const feeText = document.getElementById(type + 'FeeText');
            
            const amount = parseFloat(amountInput.value);
            
            if (amount > 0) {
                const fee = calculateFee(amount);
                feeText.textContent = `العمولة: $${fee.toFixed(2)} USDT`;
                feeInfo.classList.remove('hidden');
            } else {
                feeInfo.classList.add('hidden');
            }
        }

        function nextStep() {
            if (currentStep < 5) {
                // Hide current step
                document.getElementById(`stepContent${currentStep}`).classList.add('hidden');
                
                // Show transaction form based on type
                if (currentStep === 1) {
                    if (formData.transactionType === 'buy') {
                        document.getElementById('buyForm').classList.remove('hidden');
                        document.getElementById('sellForm').classList.add('hidden');
                    } else {
                        document.getElementById('sellForm').classList.remove('hidden');
                        document.getElementById('buyForm').classList.add('hidden');
                    }
                }
                
                // Prepare step 3 content
                if (currentStep === 2) {
                    prepareStep3();
                }
                
                // Prepare step 4 content
                if (currentStep === 3) {
                    prepareStep4();
                }
                
                currentStep++;
                
                // Show next step
                document.getElementById(`stepContent${currentStep}`).classList.remove('hidden');
                document.getElementById(`stepContent${currentStep}`).classList.add('fade-in');
                
                updateProgressBar();
            }
        }

        function prevStep() {
            if (currentStep > 1) {
                document.getElementById(`stepContent${currentStep}`).classList.add('hidden');
                currentStep--;
                document.getElementById(`stepContent${currentStep}`).classList.remove('hidden');
                document.getElementById(`stepContent${currentStep}`).classList.add('fade-in');
                updateProgressBar();
            }
        }

        function updateProgressBar() {
            // Update step indicators
            for (let i = 1; i <= 4; i++) {
                const step = document.getElementById(`step${i}`);
                if (i < currentStep) {
                    step.classList.add('completed');
                    step.classList.remove('active');
                    step.innerHTML = '<i class="fas fa-check"></i>';
                } else if (i === currentStep) {
                    step.classList.add('active');
                    step.classList.remove('completed');
                    step.textContent = i;
                } else {
                    step.classList.remove('active', 'completed');
                    step.textContent = i;
                }
            }
            
            // Update progress line
            const progressLine = document.getElementById('progressLine');
            const progressPercentage = ((currentStep - 1) / 3) * 100;
            progressLine.style.width = `${progressPercentage}%`;
        }

        function prepareStep3() {
            const isBuy = formData.transactionType === 'buy';
            
            document.getElementById('step3Title').textContent = isBuy ? 'تفاصيل الدفع' : 'تفاصيل الإرسال';
            document.getElementById('step3Description').textContent = isBuy ? 
                'استخدم التفاصيل التالية لإرسال الدفعة' : 
                'أرسل USDT إلى العنوان التالي';
            
            if (isBuy) {
                // Show payment details
                document.getElementById('paymentDetails').classList.remove('hidden');
                document.getElementById('cryptoDetails').classList.add('hidden');
                
                const paymentMethod = PAYMENT_METHODS[formData.transaction.paymentMethod];
                document.getElementById('paymentAddress').textContent = paymentMethod.address;
                
                // Update amount summary for buy
                const amount = formData.transaction.amount;
                const fee = calculateFee(amount);
                const networkFee = formData.transaction.networkFee;
                const totalAmount = (amount + fee + networkFee) * EXCHANGE_RATE;
                
                document.getElementById('amountSummary').innerHTML = `
                    <div class="summary-item">
                        <span>المبلغ الأساسي:</span>
                        <span>${amount} USDT</span>
                    </div>
                    <div class="summary-item">
                        <span>عمولة التحويل:</span>
                        <span>$${fee.toFixed(2)}</span>
                    </div>
                    <div class="summary-item">
                        <span>رسوم الشبكة (${formData.transaction.network.toUpperCase()}):</span>
                        <span>$${networkFee}</span>
                    </div>
                    <div class="summary-item">
                        <span>المبلغ الكلي:</span>
                        <span>${totalAmount.toLocaleString()} ل.س</span>
                    </div>
                `;
            } else {
                // Show crypto address
                document.getElementById('paymentDetails').classList.add('hidden');
                document.getElementById('cryptoDetails').classList.remove('hidden');
                
                const cryptoAddress = CRYPTO_ADDRESSES[formData.transaction.sellNetwork];
                document.getElementById('cryptoAddress').textContent = cryptoAddress;
                
                // Update amount summary for sell
                const amount = formData.transaction.sellAmount;
                const fee = calculateFee(amount);
                const networkFee = formData.transaction.sellNetworkFee;
                const netAmount = (amount - fee - networkFee) * EXCHANGE_RATE;
                
                document.getElementById('amountSummary').innerHTML = `
                    <div class="summary-item">
                        <span>المبلغ الأساسي:</span>
                        <span>${amount} USDT</span>
                    </div>
                    <div class="summary-item">
                        <span>عمولة التحويل:</span>
                        <span>-$${fee.toFixed(2)}</span>
                    </div>
                    <div class="summary-item">
                        <span>رسوم الشبكة (${formData.transaction.sellNetwork.toUpperCase()}):</span>
                        <span>-$${networkFee}</span>
                    </div>
                    <div class="summary-item">
                        <span>المبلغ الصافي:</span>
                        <span>${netAmount.toLocaleString()} ل.س</span>
                    </div>
                `;
            }
        }

        function prepareStep4() {
            const isBuy = formData.transactionType === 'buy';
            
            // Personal information summary
            document.getElementById('personalSummary').innerHTML = `
                <div class="summary-item">
                    <span>الاسم:</span>
                    <span>${formData.personal.name}</span>
                </div>
                <div class="summary-item">
                    <span>الهاتف:</span>
                    <span>${formData.personal.phone}</span>
                </div>
                <div class="summary-item">
                    <span>المدينة:</span>
                    <span>${formData.personal.city}</span>
                </div>
                <div class="summary-item">
                    <span>نوع العملية:</span>
                    <span>${isBuy ? 'شراء' : 'بيع'}</span>
                </div>
            `;
            
            // Transaction summary
            if (isBuy) {
                document.getElementById('transactionSummary').innerHTML = `
                    <div class="summary-item">
                        <span>الكمية:</span>
                        <span>${formData.transaction.amount} USDT</span>
                    </div>
                    <div class="summary-item">
                        <span>الشبكة:</span>
                        <span>${formData.transaction.network.toUpperCase()}</span>
                    </div>
                    <div class="summary-item">
                        <span>العنوان:</span>
                        <span>${formData.transaction.address.substring(0, 20)}...</span>
                    </div>
                    <div class="summary-item">
                        <span>طريقة الدفع:</span>
                        <span>${PAYMENT_METHODS[formData.transaction.paymentMethod].name}</span>
                    </div>
                `;
                
                document.getElementById('warningText').textContent = 
                    'يرجى إرسال المبلغ المطلوب بدقة إلى تفاصيل الدفع المحددة. سيتم تحويل USDT بعد تأكيد الدفع.';
            } else {
                document.getElementById('transactionSummary').innerHTML = `
                    <div class="summary-item">
                        <span>الكمية:</span>
                        <span>${formData.transaction.sellAmount} USDT</span>
                    </div>
                    <div class="summary-item">
                        <span>الشبكة:</span>
                        <span>${formData.transaction.sellNetwork.toUpperCase()}</span>
                    </div>
                    <div class="summary-item">
                        <span>طريقة الاستلام:</span>
                        <span>${formData.transaction.receivingMethod}</span>
                    </div>
                    <div class="summary-item">
                        <span>تفاصيل الحساب:</span>
                        <span>${formData.transaction.accountDetails}</span>
                    </div>
                `;
                
                document.getElementById('warningText').textContent = 
                    'يرجى إرسال USDT إلى العنوان المحدد. سيتم تحويل المبلغ إلى حسابك بعد تأكيد الاستلام.';
            }
        }

        function copyToClipboard(elementId) {
            const element = document.getElementById(elementId);
            const text = element.textContent;
            
            navigator.clipboard.writeText(text).then(() => {
                const button = element.nextElementSibling;
                const originalContent = button.innerHTML;
                button.innerHTML = '<i class="fas fa-check"></i> تم النسخ';
                button.classList.add('copied');
                
                setTimeout(() => {
                    button.innerHTML = originalContent;
                    button.classList.remove('copied');
                }, 2000);
            });
        }

        function submitOrder() {
            const submitBtn = document.getElementById('submitBtn');
            const originalContent = submitBtn.innerHTML;
            
            // Show loading state
            submitBtn.innerHTML = '<div class="loading-spinner"></div> جاري الإرسال...';
            submitBtn.disabled = true;
            
            // Hide any previous error messages
            document.getElementById('errorMessage').classList.add('hidden');
            
            // Prepare email data
            const emailData = prepareEmailData();
            
            // Create mailto link
            const subject = encodeURIComponent(`طلب ${formData.transactionType === 'buy' ? 'شراء' : 'بيع'} USDT - ${formData.personal.name}`);
            const body = encodeURIComponent(emailData);
            const mailtoLink = `mailto:alimahmoud001a@gmail.com?subject=${subject}&body=${body}`;
            
            // Simulate processing time
            setTimeout(() => {
                // Open email client
                window.location.href = mailtoLink;
                
                // Show success step
                submitBtn.innerHTML = originalContent;
                submitBtn.disabled = false;
                
                // Prepare final summary
                prepareFinalSummary();
                
                // Move to success step
                document.getElementById('stepContent4').classList.add('hidden');
                document.getElementById('stepContent5').classList.remove('hidden');
                document.getElementById('stepContent5').classList.add('fade-in');
                
                currentStep = 5;
                updateProgressBar();
            }, 2000);
        }

        function prepareEmailData() {
            const isBuy = formData.transactionType === 'buy';
            const timestamp = new Date().toLocaleString('ar-EG');
            
            let emailContent = `طلب ${isBuy ? 'شراء' : 'بيع'} USDT\n\n`;
            
            emailContent += `المعلومات الشخصية:\n`;
            emailContent += `الاسم: ${formData.personal.name}\n`;
            emailContent += `الهاتف: ${formData.personal.phone}\n`;
            emailContent += `المدينة: ${formData.personal.city}\n\n`;
            
            emailContent += `تفاصيل العملية:\n`;
            emailContent += `نوع العملية: ${isBuy ? 'شراء' : 'بيع'}\n`;
            
            if (isBuy) {
                const amount = formData.transaction.amount;
                const fee = calculateFee(amount);
                const networkFee = formData.transaction.networkFee;
                const totalAmount = (amount + fee + networkFee) * EXCHANGE_RATE;
                
                emailContent += `الكمية المطلوبة: ${amount} USDT\n`;
                emailContent += `الشبكة: ${formData.transaction.network.toUpperCase()}\n`;
                emailContent += `عنوان المحفظة: ${formData.transaction.address}\n`;
                emailContent += `طريقة الدفع: ${PAYMENT_METHODS[formData.transaction.paymentMethod].name}\n`;
                emailContent += `العمولة: $${fee.toFixed(2)}\n`;
                emailContent += `رسوم الشبكة: $${networkFee}\n`;
                emailContent += `المبلغ الكلي: ${totalAmount.toLocaleString()} ل.س\n`;
                
                if (formData.transaction.notes) {
                    emailContent += `ملاحظات: ${formData.transaction.notes}\n`;
                }
            } else {
                const amount = formData.transaction.sellAmount;
                const fee = calculateFee(amount);
                const networkFee = formData.transaction.sellNetworkFee;
                const netAmount = (amount - fee - networkFee) * EXCHANGE_RATE;
                
                emailContent += `الكمية المراد بيعها: ${amount} USDT\n`;
                emailContent += `الشبكة: ${formData.transaction.sellNetwork.toUpperCase()}\n`;
                emailContent += `طريقة الاستلام: ${formData.transaction.receivingMethod}\n`;
                emailContent += `تفاصيل الحساب: ${formData.transaction.accountDetails}\n`;
                emailContent += `العمولة: $${fee.toFixed(2)}\n`;
                emailContent += `رسوم الشبكة: $${networkFee}\n`;
                emailContent += `المبلغ الصافي: ${netAmount.toLocaleString()} ل.س\n`;
                
                if (formData.transaction.sellNotes) {
                    emailContent += `ملاحظات: ${formData.transaction.sellNotes}\n`;
                }
            }
            
            emailContent += `\nتاريخ الطلب: ${timestamp}\n`;
            emailContent += `رقم الطلب: #${Date.now().toString().slice(-6)}`;
            
            return emailContent;
        }

        function prepareFinalSummary() {
            const isBuy = formData.transactionType === 'buy';
            const orderId = Date.now().toString().slice(-6);
            
            document.getElementById('finalSummary').innerHTML = `
                <div class="summary-item">
                    <span>رقم الطلب:</span>
                    <span>#${orderId}</span>
                </div>
                <div class="summary-item">
                    <span>النوع:</span>
                    <span>${isBuy ? 'شراء' : 'بيع'}</span>
                </div>
                <div class="summary-item">
                    <span>المبلغ:</span>
                    <span>${isBuy ? formData.transaction.amount : formData.transaction.sellAmount} USDT</span>
                </div>
                <div class="summary-item">
                    <span>الحالة:</span>
                    <span>في انتظار المعالجة</span>
                </div>
            `;
        }

        function resetForm() {
            // Reset all form data
            formData = {
                personal: {},
                transaction: {},
                transactionType: ''
            };
            
            // Reset form inputs
            document.getElementById('fullName').value = '';
            document.getElementById('phoneNumber').value = '';
            document.getElementById('city').value = '';
            document.getElementById('buyAmount').value = '';
            document.getElementById('sellAmount').value = '';
            document.getElementById('walletAddress').value = '';
            document.getElementById('receivingMethod').value = '';
            document.getElementById('accountDetails').value = '';
            document.getElementById('buyNotes').value = '';
            document.getElementById('sellNotes').value = '';
            
            // Reset selections
            document.querySelectorAll('.selected').forEach(el => el.classList.remove('selected'));
            
            // Hide fee info
            document.getElementById('buyFeeInfo').classList.add('hidden');
            document.getElementById('sellFeeInfo').classList.add('hidden');
            
            // Reset to step 1
            currentStep = 1;
            document.querySelectorAll('.step-content').forEach(content => content.classList.add('hidden'));
            document.getElementById('stepContent1').classList.remove('hidden');
            document.getElementById('stepContent1').classList.add('fade-in');
            
            // Reset buttons
            document.getElementById('nextBtn1').disabled = true;
            document.getElementById('nextBtn2').disabled = true;
            
            updateProgressBar();
        }
    </script>
</body>
</html>

