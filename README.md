# FoodFlow - AI-Powered Meal Planning Platform

FoodFlow is a comprehensive meal planning and grocery ordering platform that uses AI to generate personalized meal plans and integrates with Zakaz.ua for seamless grocery shopping.

## Project Structure

```
FoodFlow/
├── backend/          # FastAPI backend
│   ├── app/
│   │   ├── api/      # API routes
│   │   ├── models.py # Database models
│   │   ├── schemas.py # Pydantic schemas
│   │   ├── core.py   # Core utilities (auth, etc.)
│   │   └── main.py   # FastAPI app
│   └── requirements.txt
├── frontend/         # SvelteKit frontend
│   ├── src/
│   │   ├── routes/   # SvelteKit routes
│   │   ├── lib/      # Shared utilities
│   │   └── stores/   # Svelte stores
│   └── package.json
└── specification.md  # Project specification
```

## Features

### Backend (FastAPI)
- ✅ User authentication (JWT)
- ✅ User profile and onboarding
- ✅ AI meal planning (mock service)
- ✅ Shopping cart generation
- ✅ Mock Zakaz.ua integration
- ✅ Meal tracking and statistics
- ✅ Support ticket system
- ✅ Admin panel endpoints

### Frontend (SvelteKit)
- ✅ Authentication (login/register)
- ✅ Onboarding flow
- ✅ Dashboard
- ✅ Meal planning interface
- ✅ Shopping cart
- ✅ Nutrition tracking
- ✅ User profile

## Setup Instructions

### Backend Setup

1. Navigate to backend directory:
```bash
cd backend
```

2. Create virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Run the server:
```bash
uvicorn app.main:app --reload
```

The API will be available at `http://localhost:8000`
API documentation: `http://localhost:8000/docs`

### Frontend Setup

1. Navigate to frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Run development server:
```bash
npm run dev
```

The frontend will be available at `http://localhost:5173`

## Database

The application uses SQLite for local development. The database file (`foodflow.db`) will be created automatically when you first run the backend.

## Mock Services

As per project requirements, the following services are implemented as mocks:

1. **AI Service** (`backend/app/services/ai_service.py`)
   - Generates meal plans based on user preferences
   - Filters meals by dietary restrictions
   - Provides meal replacement functionality

2. **Zakaz.ua Service** (`backend/app/services/zakaz_service.py`)
   - Maps ingredients to products
   - Generates shopping carts
   - Creates mock orders

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login (returns JWT token)
- `GET /api/auth/me` - Get current user info

### Users
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile

### Meals
- `POST /api/meals/generate` - Generate meal plan
- `GET /api/meals/current` - Get current meal plan
- `PUT /api/meals/meals/{id}/replace` - Replace a meal
- `GET /api/meals/history` - Get meal plan history

### Cart
- `POST /api/cart/generate` - Generate cart from meal plan
- `GET /api/cart/` - Get current cart
- `DELETE /api/cart/items/{id}` - Remove cart item
- `POST /api/cart/checkout` - Checkout (create order)

### Tracking
- `POST /api/tracking/log` - Log a meal
- `GET /api/tracking/progress/{date}` - Get daily progress
- `GET /api/tracking/logs` - Get meal logs

### Admin
- `GET /api/admin/users` - List users (admin only)
- `GET /api/admin/orders` - List orders (admin only)
- `GET /api/admin/stats/subscriptions` - Subscription stats (admin only)

### Support
- `POST /api/support/tickets` - Create support ticket
- `GET /api/support/tickets` - Get user tickets
- `GET /api/support/tickets/{id}` - Get ticket details

## Development Notes

- All third-party integrations (Zakaz.ua, AI, payments) are mocked for local development
- The database is SQLite for quick prototyping
- JWT tokens are stored in localStorage on the frontend
- CORS is configured to allow requests from SvelteKit dev server

## Next Steps

To extend the prototype:
1. Replace mock AI service with actual AI API integration
2. Replace mock Zakaz.ua service with real API integration
3. Add payment system integration (Stripe/LiqPay)
4. Implement push notifications
5. Add calendar integration
6. Enhance admin panel UI
7. Add more comprehensive tracking and analytics

## License

This is a prototype project for development purposes.

## Changy change
