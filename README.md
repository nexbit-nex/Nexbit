<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NEXBIT Presale - Small Bits, Big Returns</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/ethers/5.7.1/ethers.umd.min.js"></script>
    <style>
        :root {
            --primary: #2a4b8d;
            --secondary: #4a90e2;
            --accent: #f5a623;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #28a745;
            --danger: #dc3545;
            --warning: #ffc107;
            --info: #17a2b8;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo-section {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo {
            height: 50px;
            border-radius: 8px;
        }
        
        .slogan {
            font-size: 1.2rem;
            font-weight: 500;
        }
        
        .wallet-section {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .wallet-btn {
            background-color: var(--accent);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .wallet-btn:hover {
            background-color: #e0961a;
        }
        
        .wallet-address {
            background-color: rgba(255,255,255,0.2);
            padding: 8px 15px;
            border-radius: 5px;
            font-size: 0.9rem;
        }
        
        .banner {
            width: 100%;
            height: 300px;
            background-image: url('https://photos.pinksale.finance/file/pinksale-logo-upload/1759769385198-fabb7e866e13d49ebef0d54cdcd6ceb5.JPG');
            background-size: cover;
            background-position: center;
            margin-bottom: 30px;
            border-radius: 10px;
            overflow: hidden;
        }
        
        .main-content {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 30px;
            margin: 30px 0;
        }
        
        .card {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            padding: 25px;
            margin-bottom: 25px;
        }
        
        .card-title {
            font-size: 1.4rem;
            margin-bottom: 20px;
            color: var(--primary);
            border-bottom: 2px solid var(--light);
            padding-bottom: 10px;
        }
        
        .progress-section {
            margin-bottom: 25px;
        }
        
        .progress-bar {
            height: 20px;
            background-color: #e9ecef;
            border-radius: 10px;
            overflow: hidden;
            margin: 10px 0;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(to right, var(--secondary), var(--primary));
            border-radius: 10px;
            transition: width 0.5s ease;
        }
        
        .progress-info {
            display: flex;
            justify-content: space-between;
            font-size: 0.9rem;
            color: #6c757d;
        }
        
        .buy-section {
            margin-bottom: 25px;
        }
        
        .buy-options {
            display: flex;
            gap: 15px;
            margin-bottom: 15px;
        }
        
        .buy-option {
            flex: 1;
            text-align: center;
            padding: 15px;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .buy-option.active {
            border-color: var(--secondary);
            background-color: rgba(74, 144, 226, 0.05);
        }
        
        .buy-option:hover {
            border-color: var(--secondary);
        }
        
        .input-group {
            margin-bottom: 15px;
        }
        
        .input-label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }
        
        .input-with-btn {
            display: flex;
            gap: 10px;
        }
        
        .input-with-btn input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid #ced4da;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .max-btn {
            background-color: var(--light);
            border: 1px solid #ced4da;
            padding: 0 15px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 500;
        }
        
        .buy-btn {
            width: 100%;
            background: linear-gradient(to right, var(--secondary), var(--primary));
            color: white;
            border: none;
            padding: 15px;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .buy-btn:hover {
            opacity: 0.9;
        }
        
        .buy-btn:disabled {
            background: #6c757d;
            cursor: not-allowed;
        }
        
        .bonus-section {
            margin-bottom: 25px;
        }
        
        .bonus-list {
            list-style-type: none;
        }
        
        .bonus-item {
            padding: 10px 0;
            border-bottom: 1px solid #e9ecef;
            display: flex;
            justify-content: space-between;
        }
        
        .bonus-item:last-child {
            border-bottom: none;
        }
        
        .bonus-percent {
            font-weight: 600;
            color: var(--success);
        }
        
        .tier-section {
            margin-bottom: 25px;
        }
        
        .tier-list {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 10px;
        }
        
        .tier-item {
            text-align: center;
            padding: 15px 5px;
            border-radius: 8px;
            background-color: var(--light);
            transition: all 0.3s;
        }
        
        .tier-item.active {
            background-color: var(--secondary);
            color: white;
        }
        
        .tier-name {
            font-weight: 600;
            font-size: 0.9rem;
        }
        
        .tier-allocation {
            font-size: 0.8rem;
            margin-top: 5px;
        }
        
        .staking-section {
            margin-bottom: 25px;
        }
        
        .staking-plans {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 10px;
        }
        
        .staking-plan {
            text-align: center;
            padding: 15px 5px;
            border-radius: 8px;
            background-color: var(--light);
            transition: all 0.3s;
        }
        
        .staking-plan:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .staking-period {
            font-weight: 600;
            font-size: 0.9rem;
        }
        
        .staking-apy {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--success);
            margin: 5px 0;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }
        
        .social-link {
            display: inline-block;
            padding: 10px 20px;
            background-color: var(--primary);
            color: white;
            text-decoration: none;
            border-radius: 5px;
            transition: all 0.3s;
        }
        
        .social-link:hover {
            background-color: var(--secondary);
        }
        
        .user-info-section {
            margin-bottom: 25px;
        }
        
        .info-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }
        
        .info-item {
            padding: 15px;
            background-color: var(--light);
            border-radius: 8px;
            text-align: center;
        }
        
        .info-value {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .info-label {
            font-size: 0.9rem;
            color: #6c757d;
            margin-top: 5px;
        }
        
        .referral-section {
            margin-bottom: 25px;
        }
        
        .referral-input {
            display: flex;
            gap: 10px;
        }
        
        .referral-input input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid #ced4da;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .referral-btn {
            background-color: var(--accent);
            color: white;
            border: none;
            padding: 0 20px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
        }
        
        footer {
            background-color: var(--dark);
            color: white;
            padding: 30px 0;
            text-align: center;
            margin-top: 50px;
        }
        
        .footer-content {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .contract-address {
            background-color: rgba(255,255,255,0.1);
            padding: 10px 15px;
            border-radius: 5px;
            font-family: monospace;
            margin: 15px 0;
            word-break: break-all;
        }
        
        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
            
            .tier-list, .staking-plans {
                grid-template-columns: repeat(3, 1fr);
            }
            
            .info-grid {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 576px) {
            .header-content {
                flex-direction: column;
                gap: 15px;
            }
            
            .tier-list, .staking-plans {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .buy-options {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo-section">
                    <img src="https://photos.pinksale.finance/file/pinksale-logo-upload/1759769706757-a112fb0cb7d0fff59069a55924092519.JPG" alt="NEXBIT Logo" class="logo">
                    <div>
                        <h1>NEXBIT</h1>
                        <div class="slogan">Small Bits, Big Returns</div>
                    </div>
                </div>
                <div class="wallet-section">
                    <button class="wallet-btn" id="connectWallet">Connect Wallet</button>
                    <div class="wallet-address" id="walletAddress" style="display: none;"></div>
                </div>
            </div>
        </div>
    </header>

    <div class="container">
        <div class="banner"></div>
        
        <div class="main-content">
            <div class="left-column">
                <div class="card">
                    <h2 class="card-title">Presale Progress</h2>
                    <div class="progress-section">
                        <div class="progress-bar">
                            <div class="progress-fill" id="progressFill" style="width: 0%"></div>
                        </div>
                        <div class="progress-info">
                            <span id="tokensSold">0 NEX</span>
                            <span id="progressPercent">0%</span>
                            <span id="totalSupply">5,400,000 NEX</span>
                        </div>
                    </div>
                    
                    <div class="buy-section">
                        <h3 class="card-title">Buy NEX Tokens</h3>
                        
                        <div class="buy-options">
                            <div class="buy-option active" data-currency="usdt">USDT</div>
                            <div class="buy-option" data-currency="usdc">USDC</div>
                            <div class="buy-option" data-currency="core">CORE</div>
                        </div>
                        
                        <div class="input-group">
                            <label class="input-label">Amount to Pay</label>
                            <div class="input-with-btn">
                                <input type="number" id="paymentAmount" placeholder="Enter amount">
                                <button class="max-btn" id="maxBtn">MAX</button>
                            </div>
                        </div>
                        
                        <div class="input-group">
                            <label class="input-label">You Will Receive</label>
                            <input type="text" id="tokenAmount" placeholder="0 NEX" readonly>
                        </div>
                        
                        <div class="input-group">
                            <label class="input-label">Referral Code (Optional)</label>
                            <input type="text" id="referralCode" placeholder="Enter referral address">
                        </div>
                        
                        <button class="buy-btn" id="buyBtn" disabled>Connect Wallet to Buy</button>
                    </div>
                </div>
                
                <div class="card">
                    <h2 class="card-title">Early Bird Bonus</h2>
                    <div class="bonus-section">
                        <ul class="bonus-list">
                            <li class="bonus-item">
                                <span>First 24 Hours</span>
                                <span class="bonus-percent">25% Bonus</span>
                            </li>
                            <li class="bonus-item">
                                <span>First 3 Days</span>
                                <span class="bonus-percent">15% Bonus</span>
                            </li>
                            <li class="bonus-item">
                                <span>First 7 Days</span>
                                <span class="bonus-percent">10% Bonus</span>
                            </li>
                            <li class="bonus-item">
                                <span>First 14 Days</span>
                                <span class="bonus-percent">5% Bonus</span>
                            </li>
                        </ul>
                    </div>
                    
                    <h2 class="card-title">Tier System</h2>
                    <div class="tier-section">
                        <div class="tier-list">
                            <div class="tier-item">
                                <div class="tier-name">Bronze</div>
                                <div class="tier-allocation">+5%</div>
                            </div>
                            <div class="tier-item">
                                <div class="tier-name">Silver</div>
                                <div class="tier-allocation">+10%</div>
                            </div>
                            <div class="tier-item">
                                <div class="tier-name">Gold</div>
                                <div class="tier-allocation">+15%</div>
                            </div>
                            <div class="tier-item">
                                <div class="tier-name">Platinum</div>
                                <div class="tier-allocation">+20%</div>
                            </div>
                            <div class="tier-item">
                                <div class="tier-name">Diamond</div>
                                <div class="tier-allocation">+25%</div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="card">
                    <h2 class="card-title">Staking with Spectacular APY</h2>
                    <div class="staking-section">
                        <div class="staking-plans">
                            <div class="staking-plan">
                                <div class="staking-period">1 Month</div>
                                <div class="staking-apy">100% APY</div>
                            </div>
                            <div class="staking-plan">
                                <div class="staking-period">2 Months</div>
                                <div class="staking-apy">150% APY</div>
                            </div>
                            <div class="staking-plan">
                                <div class="staking-period">3 Months</div>
                                <div class="staking-apy">200% APY</div>
                            </div>
                            <div class="staking-plan">
                                <div class="staking-period">6 Months</div>
                                <div class="staking-apy">300% APY</div>
                            </div>
                            <div class="staking-plan">
                                <div class="staking-period">12 Months</div>
                                <div class="staking-apy">600% APY</div>
                            </div>
                        </div>
                        <p style="margin-top: 15px; text-align: center; font-size: 0.9rem;">
                            Minimum: 1 NEX per stake | Maximum: 100,000 NEX per stake
                        </p>
                    </div>
                </div>
            </div>
            
            <div class="right-column">
                <div class="card">
                    <h2 class="card-title">Your Information</h2>
                    <div class="user-info-section">
                        <div class="info-grid">
                            <div class="info-item">
                                <div class="info-value" id="userAllocation">0</div>
                                <div class="info-label">Total Allocation</div>
                            </div>
                            <div class="info-item">
                                <div class="info-value" id="userClaimed">0</div>
                                <div class="info-label">Claimed</div>
                            </div>
                            <div class="info-item">
                                <div class="info-value" id="userClaimable">0</div>
                                <div class="info-label">Claimable Now</div>
                            </div>
                            <div class="info-item">
                                <div class="info-value" id="userTier">-</div>
                                <div class="info-label">Your Tier</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="referral-section">
                        <h3 class="card-title">Referral Program</h3>
                        <p style="margin-bottom: 15px;">
                            Get 5% bonus for referring buyers, and buyers get 3% bonus!
                        </p>
                        <div class="referral-input">
                            <input type="text" id="setReferralCode" placeholder="Enter referrer address">
                            <button class="referral-btn" id="setReferralBtn">Set Referrer</button>
                        </div>
                        <div style="margin-top: 15px;">
                            <p>Your Referral Link:</p>
                            <div class="contract-address" id="referralLink">
                                Connect wallet to generate
                            </div>
                        </div>
                    </div>
                    
                    <div style="margin-top: 20px;">
                        <button class="buy-btn" id="claimBtn" disabled>Claim Tokens</button>
                    </div>
                </div>
                
                <div class="card">
                    <h2 class="card-title">Connect With Us</h2>
                    <div class="social-links">
                        <a href="https://x.com/nexbit_nex" class="social-link" target="_blank">Twitter</a>
                        <a href="https://t.me/nexbit_nex" class="social-link" target="_blank">Telegram</a>
                    </div>
                </div>
                
                <div class="card">
                    <h2 class="card-title">Contract Information</h2>
                    <p style="margin-bottom: 10px;">Token Contract:</p>
                    <div class="contract-address">0xe6EaDB7CEcC7D27E94a2058E3C728bEc8Cf4027f</div>
                    
                    <p style="margin: 15px 0 10px;">Presale Contract:</p>
                    <div class="contract-address" id="presaleContract">Loading...</div>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <div class="container">
            <div class="footer-content">
                <h3>NEXBIT - Small Bits, Big Returns</h3>
                <p>24 months linear vesting | Secure and transparent presale</p>
                <p style="margin-top: 20px; font-size: 0.9rem;">
                    &copy; 2024 NEXBIT. All rights reserved.
                </p>
            </div>
        </div>
    </footer>

    <script>
        // Contract addresses and ABI
        const TOKEN_CONTRACT = "0xe6EaDB7CEcC7D27E94a2058E3C728bEc8Cf4027f";
        const PRESALE_CONTRACT = "0xe6EaDB7CEcC7D27E94a2058E3C728bEc8Cf4027f"; // Same as token for demo
        
        // Presale contract ABI (simplified for demo)
        const presaleABI = [
            "function buyWithNative(address referrer) external payable",
            "function buyWithUSDT(uint256 usdtAmount, address referrer) external",
            "function claimTokens() external",
            "function setReferrer(address referrer) external",
            "function getUserBasicInfo(address user) public view returns (uint256 totalAllocation, uint256 totalClaimed, uint256 claimableNow)",
            "function getUserBonusInfo(address user) public view returns (uint256 bonusAllocation, uint256 referralBonus, uint8 tier)",
            "function getUserContributionInfo(address user) public view returns (uint256 totalContributionUSDT, uint256 totalContributionNative)",
            "function getPresaleProgress() public view returns (uint256 soldPercent, uint256 raisedUSDT)",
            "function getTimeRemaining() public view returns (uint256 daysLeft, uint256 hoursLeft)",
            "function getTokenAmount(uint256 paymentAmount, bool isNative) public pure returns (uint256)",
            "function getCurrentEarlyBirdBonus() public view returns (uint256 bonusPercent, uint256 timeRemaining)",
            "function totalSold() public view returns (uint256)",
            "function presaleActive() public view returns (bool)"
        ];
        
        // Global variables
        let provider;
        let signer;
        let presaleContract;
        let userAddress;
        let selectedCurrency = 'usdt';
        
        // DOM elements
        const connectWalletBtn = document.getElementById('connectWallet');
        const walletAddressEl = document.getElementById('walletAddress');
        const buyBtn = document.getElementById('buyBtn');
        const claimBtn = document.getElementById('claimBtn');
        const paymentAmountInput = document.getElementById('paymentAmount');
        const tokenAmountInput = document.getElementById('tokenAmount');
        const referralCodeInput = document.getElementById('referralCode');
        const setReferralBtn = document.getElementById('setReferralBtn');
        const setReferralCodeInput = document.getElementById('setReferralCode');
        const maxBtn = document.getElementById('maxBtn');
        const progressFill = document.getElementById('progressFill');
        const progressPercent = document.getElementById('progressPercent');
        const tokensSold = document.getElementById('tokensSold');
        const userAllocation = document.getElementById('userAllocation');
        const userClaimed = document.getElementById('userClaimed');
        const userClaimable = document.getElementById('userClaimable');
        const userTier = document.getElementById('userTier');
        const referralLink = document.getElementById('referralLink');
        const presaleContractEl = document.getElementById('presaleContract');
        const buyOptions = document.querySelectorAll('.buy-option');
        
        // Initialize
        document.addEventListener('DOMContentLoaded', function() {
            presaleContractEl.textContent = PRESALE_CONTRACT;
            updateTokenAmount();
            
            // Event listeners
            connectWalletBtn.addEventListener('click', connectWallet);
            buyBtn.addEventListener('click', buyTokens);
            claimBtn.addEventListener('click', claimTokens);
            paymentAmountInput.addEventListener('input', updateTokenAmount);
            maxBtn.addEventListener('click', setMaxAmount);
            setReferralBtn.addEventListener('click', setReferrer);
            
            // Buy option selection
            buyOptions.forEach(option => {
                option.addEventListener('click', function() {
                    buyOptions.forEach(opt => opt.classList.remove('active'));
                    this.classList.add('active');
                    selectedCurrency = this.getAttribute('data-currency');
                    updateTokenAmount();
                });
            });
            
            // Check if wallet is already connected
            if (typeof window.ethereum !== 'undefined') {
                window.ethereum.request({ method: 'eth_accounts' })
                    .then(accounts => {
                        if (accounts.length > 0) {
                            userAddress = accounts[0];
                            initializeContract();
                            updateUI();
                        }
                    });
            }
        });
        
        // Connect wallet function
        async function connectWallet() {
            if (typeof window.ethereum !== 'undefined') {
                try {
                    const accounts = await window.ethereum.request({ 
                        method: 'eth_requestAccounts' 
                    });
                    userAddress = accounts[0];
                    initializeContract();
                    updateUI();
                } catch (error) {
                    console.error('Error connecting wallet:', error);
                    alert('Error connecting wallet. Please try again.');
                }
            } else {
                alert('Please install MetaMask or another Web3 wallet to continue.');
            }
        }
        
        // Initialize contract connection
        async function initializeContract() {
            provider = new ethers.providers.Web3Provider(window.ethereum);
            signer = provider.getSigner();
            presaleContract = new ethers.Contract(PRESALE_CONTRACT, presaleABI, signer);
            
            // Update wallet UI
            walletAddressEl.textContent = `${userAddress.substring(0, 6)}...${userAddress.substring(userAddress.length - 4)}`;
            walletAddressEl.style.display = 'block';
            connectWalletBtn.textContent = 'Connected';
            
            // Enable buttons
            buyBtn.disabled = false;
            buyBtn.textContent = 'Buy NEX Tokens';
            claimBtn.disabled = false;
            
            // Update referral link
            referralLink.textContent = `${window.location.origin}?ref=${userAddress}`;
        }
        
        // Update UI with user data
        async function updateUI() {
            if (!presaleContract || !userAddress) return;
            
            try {
                // Get user info
                const [basicInfo, bonusInfo, contributionInfo] = await Promise.all([
                    presaleContract.getUserBasicInfo(userAddress),
                    presaleContract.getUserBonusInfo(userAddress),
                    presaleContract.getUserContributionInfo(userAddress)
                ]);
                
                // Update user info display
                const totalAllocation = parseFloat(ethers.utils.formatUnits(basicInfo.totalAllocation, 18));
                const totalClaimed = parseFloat(ethers.utils.formatUnits(basicInfo.totalClaimed, 18));
                const claimableNow = parseFloat(ethers.utils.formatUnits(basicInfo.claimableNow, 18));
                
                userAllocation.textContent = totalAllocation.toFixed(2);
                userClaimed.textContent = totalClaimed.toFixed(2);
                userClaimable.textContent = claimableNow.toFixed(2);
                
                // Update tier
                const tierNames = ['Bronze', 'Silver', 'Gold', 'Platinum', 'Diamond'];
                userTier.textContent = tierNames[bonusInfo.tier] || '-';
                
                // Update presale progress
                const progress = await presaleContract.getPresaleProgress();
                const soldPercent = progress.soldPercent.toNumber();
                const totalSoldAmount = await presaleContract.totalSold();
                const formattedSold = parseFloat(ethers.utils.formatUnits(totalSoldAmount, 18)).toLocaleString();
                
                progressFill.style.width = `${soldPercent}%`;
                progressPercent.textContent = `${soldPercent}%`;
                tokensSold.textContent = `${formattedSold} NEX`;
                
                // Update early bird bonus
                const bonusInfoCurrent = await presaleContract.getCurrentEarlyBirdBonus();
                if (bonusInfoCurrent.bonusPercent > 0) {
                    // Highlight current bonus period in UI
                    document.querySelectorAll('.bonus-item').forEach((item, index) => {
                        if (index === 0 && bonusInfoCurrent.timeRemaining <= 24 * 60 * 60) {
                            item.style.backgroundColor = 'rgba(40, 167, 69, 0.1)';
                        } else if (index === 1 && bonusInfoCurrent.timeRemaining <= 3 * 24 * 60 * 60) {
                            item.style.backgroundColor = 'rgba(40, 167, 69, 0.1)';
                        } else if (index === 2 && bonusInfoCurrent.timeRemaining <= 7 * 24 * 60 * 60) {
                            item.style.backgroundColor = 'rgba(40, 167, 69, 0.1)';
                        } else if (index === 3 && bonusInfoCurrent.timeRemaining <= 14 * 24 * 60 * 60) {
                            item.style.backgroundColor = 'rgba(40, 167, 69, 0.1)';
                        }
                    });
                }
                
            } catch (error) {
                console.error('Error updating UI:', error);
            }
        }
        
        // Update token amount based on payment
        async function updateTokenAmount() {
            const paymentAmount = paymentAmountInput.value;
            
            if (!paymentAmount || paymentAmount <= 0) {
                tokenAmountInput.value = '0 NEX';
                return;
            }
            
            // In a real implementation, we would call the contract
            // For demo purposes, we'll calculate locally
            let tokenAmount;
            const paymentWei = ethers.utils.parseUnits(paymentAmount, 18);
            
            if (selectedCurrency === 'core') {
                // 0.25 CORE per NEX
                tokenAmount = paymentWei.div(ethers.utils.parseUnits("0.25", 18));
            } else {
                // 0.1 USDT/USDC per NEX
                tokenAmount = paymentWei.div(ethers.utils.parseUnits("0.1", 18));
            }
            
            const formattedAmount = parseFloat(ethers.utils.formatUnits(tokenAmount, 18)).toFixed(2);
            tokenAmountInput.value = `${formattedAmount} NEX`;
        }
        
        // Set maximum purchase amount
        function setMaxAmount() {
            if (selectedCurrency === 'core') {
                paymentAmountInput.value = '2500'; // MAX_BUY_NATIVE
            } else {
                paymentAmountInput.value = '1000'; // MAX_BUY_USDT
            }
            updateTokenAmount();
        }
        
        // Buy tokens function
        async function buyTokens() {
            if (!presaleContract || !userAddress) {
                alert('Please connect your wallet first.');
                return;
            }
            
            const paymentAmount = paymentAmountInput.value;
            if (!paymentAmount || paymentAmount <= 0) {
                alert('Please enter a valid amount.');
                return;
            }
            
            const referrer = referralCodeInput.value || ethers.constants.AddressZero;
            
            try {
                buyBtn.disabled = true;
                buyBtn.textContent = 'Processing...';
                
                if (selectedCurrency === 'core') {
                    // Buy with native CORE
                    const paymentWei = ethers.utils.parseEther(paymentAmount);
                    const tx = await presaleContract.buyWithNative(referrer, { value: paymentWei });
                    await tx.wait();
                } else {
                    // Buy with USDT or USDC
                    // In a real implementation, we would need to approve the token first
                    const paymentWei = ethers.utils.parseUnits(paymentAmount, 18);
                    const tx = await presaleContract.buyWithUSDT(paymentWei, referrer);
                    await tx.wait();
                }
                
                alert('Purchase successful!');
                paymentAmountInput.value = '';
                updateTokenAmount();
                updateUI();
                
            } catch (error) {
                console.error('Error buying tokens:', error);
                alert('Error buying tokens. Please try again.');
            } finally {
                buyBtn.disabled = false;
                buyBtn.textContent = 'Buy NEX Tokens';
            }
        }
        
        // Claim tokens function
        async function claimTokens() {
            if (!presaleContract || !userAddress) {
                alert('Please connect your wallet first.');
                return;
            }
            
            try {
                claimBtn.disabled = true;
                claimBtn.textContent = 'Claiming...';
                
                const tx = await presaleContract.claimTokens();
                await tx.wait();
                
                alert('Tokens claimed successfully!');
                updateUI();
                
            } catch (error) {
                console.error('Error claiming tokens:', error);
                alert('Error claiming tokens. Please try again.');
            } finally {
                claimBtn.disabled = false;
                claimBtn.textContent = 'Claim Tokens';
            }
        }
        
        // Set referrer function
        async function setReferrer() {
            if (!presaleContract || !userAddress) {
                alert('Please connect your wallet first.');
                return;
            }
            
            const referrer = setReferralCodeInput.value;
            if (!referrer || !ethers.utils.isAddress(referrer)) {
                alert('Please enter a valid referrer address.');
                return;
            }
            
            try {
                setReferralBtn.disabled = true;
                setReferralBtn.textContent = 'Setting...';
                
                const tx = await presaleContract.setReferrer(referrer);
                await tx.wait();
                
                alert('Referrer set successfully!');
                setReferralCodeInput.value = '';
                
            } catch (error) {
                console.error('Error setting referrer:', error);
                alert('Error setting referrer. Please try again.');
            } finally {
                setReferralBtn.disabled = false;
                setReferralBtn.textContent = 'Set Referrer';
            }
        }
        
        // Listen for account changes
        if (typeof window.ethereum !== 'undefined') {
            window.ethereum.on('accountsChanged', function(accounts) {
                if (accounts.length === 0) {
                    // User disconnected their wallet
                    userAddress = null;
                    walletAddressEl.style.display = 'none';
                    connectWalletBtn.textContent = 'Connect Wallet';
                    buyBtn.disabled = true;
                    buyBtn.textContent = 'Connect Wallet to Buy';
                    claimBtn.disabled = true;
                } else {
                    // User switched accounts
                    userAddress = accounts[0];
                    initializeContract();
                    updateUI();
                }
            });
        }
    </script>
</body>
</html>
