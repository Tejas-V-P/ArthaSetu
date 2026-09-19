# ArthaSetu

> **Bridge your spending to your goals.**

ArthaSetu is a cross-platform personal finance and expense-tracking application that helps users understand their money, control monthly spending, and make steady progress toward savings goals.

The name combines **Artha**—a Sanskrit idea of meaningful prosperity and livelihood—with **Setu**, meaning bridge. The app is designed to bridge everyday financial decisions and long-term financial well-being.

## Features

- Secure account creation and sign-in
- Add, edit, and delete income and expense transactions
- Organize transactions by category, wallet, and payment method
- Set monthly budgets and track remaining spending limits
- Create savings goals and monitor progress
- View dashboards for monthly income, expenses, balance, and category-wise spending
- Search and filter transactions by date, category, type, or wallet
- Create recurring transactions for regular bills, subscriptions, or income
- Receive budget-limit alerts and spending insights
- Export transaction history to CSV

## Tech Stack

| Layer | Technology |
| --- | --- |
| Client application | Flutter, Dart |
| State management | Riverpod |
| Routing | GoRouter |
| Backend and authentication | Supabase Auth and Supabase APIs |
| Relational database | PostgreSQL |
| Data visualization | `fl_chart` |
| Local preferences / cache | SharedPreferences or Hive |
| Version control | Git and GitHub |

## Problem Statement

People often track expenses manually, across multiple bank apps, or not at all. This makes it difficult to identify spending patterns, stay within a budget, and plan for goals.

ArthaSetu provides one simple space to record financial activity, visualize habits, and act on clear insights. It is especially useful for students, young professionals, and families who want a practical view of their finances.

## Database Design

ArthaSetu uses a normalized PostgreSQL relational schema. Each user owns wallets, categories, transactions, budgets, and savings goals, while foreign keys preserve data integrity.

```text
users
 ├── wallets
 ├── categories
 ├── transactions
 │    ├── wallet_id → wallets.id
 │    └── category_id → categories.id
 ├── budgets
 │    └── category_id → categories.id
 └── savings_goals
```

### Key tables

| Table | Purpose |
| --- | --- |
| `users` | Stores authenticated user profiles. |
| `wallets` | Stores cash, bank-account, and digital-wallet balances. |
| `categories` | Stores customizable income and expense categories. |
| `transactions` | Stores each income, expense, or transfer with its amount and date. |
| `budgets` | Stores category-wise monthly budget limits. |
| `savings_goals` | Stores target amounts, saved amounts, and goal deadlines. |

## Architecture

```text
Flutter UI
   ↓
Riverpod Providers / Controllers
   ↓
Repositories
   ↓
Supabase Client
   ↓
Supabase Auth + PostgreSQL Database
```

The repository layer keeps UI code independent of database operations, making the app easier to test, scale, and maintain.

## Getting Started

### Prerequisites

- Flutter SDK (stable channel)
- Dart SDK
- A Supabase project with PostgreSQL enabled
- Android Studio, VS Code, or another Flutter-supported editor

### Installation

1. Clone the repository.

   ```bash
   git clone https://github.com/<your-username>/arthasetu.git
   cd arthasetu
   ```

2. Install dependencies.

   ```bash
   flutter pub get
   ```

3. Add your Supabase project URL and anonymous key to a local environment/configuration file. Never commit production secrets.

4. Run the app.

   ```bash
   flutter run
   ```

## Screens to Include

Add screenshots or a short demo video after building the app:

- Sign-in / sign-up screen
- Dashboard with income, expense, and balance summaries
- Add transaction form
- Transaction history with filters
- Budget tracking screen
- Savings-goal progress screen

## Future Enhancements

- Receipt scanning with OCR
- Automatic bank/SMS transaction import where supported
- Multi-currency tracking
- Shared household budgets
- Scheduled reminders and notifications
- AI-generated savings suggestions based on spending patterns
- Cloud sync and offline-first support

## Learning Outcomes

- Designed a normalized relational database using primary keys, foreign keys, indexes, and row-level security.
- Built responsive Flutter interfaces for mobile and web using reusable components.
- Applied Riverpod to manage asynchronous app state cleanly.
- Implemented secure authentication and user-specific data access through Supabase.
- Developed financial analytics and charts from transactional data.

## Resume Description

**Built ArthaSetu, a cross-platform personal-finance tracker using Flutter, Dart, Supabase, and PostgreSQL. Implemented secure authentication, normalized relational data models, expense and budget tracking, savings goals, searchable transaction history, and visual spending analytics.**

## License

This project is available under the MIT License. See `LICENSE` for details.
