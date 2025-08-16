# Weather App Deployment Documentation

## Backend Deployment (Render)
1. Push backend repo to GitHub if not done already.
2. Deploy on Render:
   - Select **Web Service**
   - Connect GitHub repo
   - Set build command: `pip install -r requirements.txt`
   - Start command: `gunicorn main:app -w 4 -k uvicorn.workers.UvicornWorker`
   - Set environment variables (e.g., PORT, API keys)
3. Your backend URL: `https://weather-app-backend-pvbh.onrender.com`

## Frontend Deployment (Vercel)
1. Push frontend repo to GitHub if not done already.
2. Deploy on Vercel:
   - Connect GitHub repo
   - Set **Environment Variable**: `REACT_APP_BACKEND_URL=https://weather-app-backend-pvbh.onrender.com`
3. Your frontend URL: `https://weather-app-frontend-xyz.vercel.app`

## Running Locally
1. Backend:
   ```bash
   cd backend
   pip install -r requirements.txt
   uvicorn main:app --reload
