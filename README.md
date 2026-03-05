# TallyUP
A Sleek, AI-Powered Personal Finance & Expense Tracker

TallyUp is a modern SwiftUI application designed to simplify financial management. Built with a focus on high-performance UI and real-time cloud synchronization, TallyUp allows users to manage multiple wallets, scan physical receipts using AI-driven OCR, and track spending patterns with ease.

# Key Features

- Smart Receipt Scanning (OCR)
Leverages Apple's Vision and VisionKit frameworks to extract data from physical receipts.
Auto-Fill: Automatically detects store names and total amounts.
Wallet Integration: Log scanned expenses directly to a specific wallet with a single tap.

- Real-Time Cloud Sync
Powered by Firebase Firestore, TallyUp ensures your data is safe and accessible across devices.
State Persistence: Custom-built AppData environment object handles debounced cloud syncing to prevent API rate-limiting while typing.
Offline Ready: Uses local state observers to ensure the UI is snappy even before the cloud updates.

- Multi-Wallet Management
Manage different accounts like Cash, Debit Cards, and E-Wallets.
Balance Tracking: Automatic calculations for income and expenses per wallet.
Visual Customization: Color-coded cards for quick identification.

- Privacy & Security
Stealth Mode: A global "Privacy Eye" toggle that hides balances and transaction amounts across the app using **** placeholders.
Secure Auth: Integrated Firebase Authentication supporting standard Email/Password and Google Sign-In.
Edge-Swipe Navigation: Custom gesture-based navigation for a cleaner, button-less authentication flow.

- Data Export
Excel/CSV Export: Generate detailed transaction reports directly from the app.
Email Integration: Uses MessageUI to send formatted reports to your registered email for further analysis in Excel or Google Sheets.

- Tech Stack
Language: Swift 5.10+
Framework: SwiftUI
Backend: Firebase (Auth & Firestore)
AI/OCR: Vision Framework, VisionKit
Architecture: MVVM (Model-View-ViewModel) with an EnvironmentObject "Source of Truth."
Concurrency: Swift Concurrency (Async/Await) for image processing and network calls.

- Project Structure
File	Description
AppData.swift	The brain of the app. Manages global state, Firebase listeners, and business logic.
UnifiedNavBar.swift	A custom-built floating navigation bar with morphing animations and a "Slide to Log" gesture.
HomeView.swift	Fast-entry keypad for manual expense/income logging.
LogView.swift	Detailed transaction history with advanced filtering and CSV export logic.
ScannerView.swift	UI and logic for the document camera and text recognition.
AuthView.swift	A unified container for the login/signup experience with edge-swipe gestures.
AccountView.swift	User profile management including Firestore-synced personal details and profile photo processing.
