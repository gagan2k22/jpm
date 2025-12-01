# OPEX Management System

A comprehensive web-based OPEX (Operational Expenditure) Management System built with Node.js, Express, React, and Prisma.

## Features

- 🔐 **Authentication & Authorization**: JWT-based auth with role-based access control
- 📊 **Dashboard**: Real-time KPIs, charts, and analytics
- 💰 **Budget Management**: Track budgets by tower, budget head, and cost centre
- 🛒 **PO Management**: Complete purchase order lifecycle with approval workflows
- 📈 **Actuals Tracking**: Monitor actual expenses and variance analysis
- 🗂️ **Master Data**: Manage towers, budget heads, vendors, and cost centres
- 📱 **Responsive Design**: Modern Material-UI interface

## Tech Stack

### Backend
- Node.js + Express
- Prisma ORM
- SQLite (dev) / PostgreSQL (production)
- JWT Authentication
- bcryptjs for password hashing

### Frontend
- React 18
- Material-UI (MUI)
- React Router
- Recharts for data visualization
- Axios for API calls

## Getting Started

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn

### Installation

1. **Clone the repository**
```bash
cd "c:/Users/rc/Documents/New folder"
```

2. **Install Backend Dependencies**
```bash
cd server
npm install
```

3. **Setup Database**
```bash
# Generate Prisma Client
npx prisma generate

# Run migrations
npx prisma migrate dev --name init

# Seed the database
node seed.js
```

4. **Install Frontend Dependencies**
```bash
cd ../client
npm install
```

### Running the Application

1. **Start Backend Server** (in `server/` directory)
```bash
npm run dev
```
Server runs on http://localhost:5000

2. **Start Frontend** (in `client/` directory)
```bash
npm run dev
```
Frontend runs on http://localhost:3000

### Default Login Credentials
- **Email**: admin@example.com
- **Password**: password123

## Project Structure

```
.
├── server/
│   ├── prisma/
│   │   └── schema.prisma          # Database schema
│   ├── src/
│   │   ├── controllers/           # Route controllers
│   │   ├── middleware/            # Auth middleware
│   │   ├── routes/                # API routes
│   │   ├── app.js                 # Express app
│   │   └── prisma.js              # Prisma client
│   ├── .env                       # Environment variables
│   ├── package.json
│   └── seed.js                    # Database seeding
│
└── client/
    ├── src/
    │   ├── components/            # Reusable components
    │   ├── context/               # React context (Auth)
    │   ├── pages/                 # Page components
    │   ├── App.jsx                # Main app component
    │   └── main.jsx               # Entry point
    ├── index.html
    ├── package.json
    └── vite.config.js

```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login

### Master Data
- `GET /api/master/towers` - Get all towers
- `POST /api/master/towers` - Create tower
- `GET /api/master/budget-heads` - Get all budget heads
- `POST /api/master/budget-heads` - Create budget head
- `GET /api/master/vendors` - Get all vendors
- `POST /api/master/vendors` - Create vendor
- `GET /api/master/cost-centres` - Get all cost centres
- `POST /api/master/cost-centres` - Create cost centre

### Budgets
- `GET /api/budgets?fiscal_year=2025` - Get budgets
- `POST /api/budgets` - Create budget
- `PUT /api/budgets/:id` - Update budget

### Purchase Orders
- `GET /api/pos` - Get all POs
- `GET /api/pos/:id` - Get PO by ID
- `POST /api/pos` - Create PO
- `PUT /api/pos/:id/status` - Update PO status

### Actuals
- `GET /api/actuals?fiscal_year=2025&month=4` - Get actuals
- `POST /api/actuals` - Create actual entry

## Database Schema

The system uses the following main entities:
- **Users & Roles**: Authentication and authorization
- **Towers**: Organizational units
- **Budget Heads**: Budget categories
- **Vendors**: Supplier information
- **Cost Centres**: Cost allocation units
- **Budget BOA**: Budget allocation
- **POs & Line Items**: Purchase orders
- **Actuals**: Actual expenses
- **Audit Logs**: Change tracking

## Future Enhancements

- Excel import/export functionality
- Advanced reporting and analytics
- Email notifications for approvals
- Multi-level approval workflows
- Azure AD / SSO integration
- Mobile app

## License

MIT
