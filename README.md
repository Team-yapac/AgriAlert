# 🌾 Welcome to **AgriAlert**

## 🌐 Project Info

**Website**: [[(https://agrialert-627730094321.us-central1.run.app/)](https://agrialert-627730094321.us-central1.run.app/)]
**GitHub Repository**: [https://github.com/Team-yapac/AgriAlert.git](https://github.com/Team-yapac/AgriAlert.git)

AgriAlert is a smart agricultural assistant that provides farmers with real-time weather alerts, AI-driven advice, and crop-specific guidance to make informed decisions and protect their livelihood.

---

## 🛠 Technologies Used

- Vite
- TypeScript
- React
- Tailwind CSS
- shadcn-ui
- Firebase Authentication
- Google Gemini
- OpenWeatherMap API

---

## 🔒 Authentication Features

- ✅ Google Sign-In via Firebase
- ✅ Email/Password Sign-Up and Login via Firebase

---

## 🌤️ Weather & AI Integration

- ✅ Real-time and forecasted weather via **OpenWeatherMap API**
- ✅ Requests permission to get user location for localized weather info
- ✅ Smart Weather Alerts (Real-Time and Predictive)
- ✅ Gemini AI for weather advice, planting schedules, and more
- ✅ Image-based advice with Gemini
- ✅ Recommended actions based on weather and crop-specific needs
- ✅ Crop Damage Reporting Tool with AI-powered photo assessment
- ✅ Voice Assistant designed for low-literacy users
- ✅ Crop-Specific Disaster Advice

> Weather data from OpenWeatherMap is sent to Gemini for more accurate, contextual AI responses.

---

## ⚙️ How to Set Up Locally

Make sure you have **Node.js & npm** installed – [Install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating)

### Clone and Run the Project

```sh
# Step 1: Clone the repository
git clone https://github.com/Team-yapac/AgriAlert.git

# Step 2: Navigate to the project directory
cd AgriAlert

# Step 3: Install dependencies
npm i

# Step 4: Start the development server
npm run dev
```

---

## 🚀 Deploying to Google Cloud Run

AgriAlert can be deployed to Google Cloud Run for a scalable, serverless hosting solution.

### Prerequisites

1. [Google Cloud Account](https://cloud.google.com/) with billing enabled
2. [Google Cloud SDK](https://cloud.google.com/sdk/docs/install) installed
3. [Docker](https://docs.docker.com/get-docker/) installed

### Deployment Steps

#### Option 1: Using the Deployment Scripts

```sh
# For Windows users
npm run deploy

# For Linux/macOS users
chmod +x deploy-to-cloud-run.sh
npm run deploy:unix
```

#### Option 2: Manual Deployment

```sh
# Step 1: Build the Docker image
# Replace YOUR_PROJECT_ID with your Google Cloud Project ID
docker build -t gcr.io/YOUR_PROJECT_ID/agrialert .

# Step 2: Configure Docker to use Google Cloud as a credential helper
gcloud auth configure-docker

# Step 3: Push the image to Google Container Registry
docker push gcr.io/YOUR_PROJECT_ID/agrialert

# Step 4: Deploy to Cloud Run
gcloud run deploy agrialert \
  --image gcr.io/YOUR_PROJECT_ID/agrialert \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated
```

### Environment Variables

When deploying to Google Cloud Run, you'll need to set up environment variables for your API keys. You can do this in the Google Cloud Console:

1. Go to Cloud Run in the Google Cloud Console
2. Select your service
3. Click "Edit & Deploy New Revision"
4. Under "Container, Networking, Security", add your environment variables
5. Deploy the new revision

### Continuous Deployment with Cloud Build

For automated deployments from your Git repository:

1. Connect your repository to Google Cloud Build
2. Use the provided `cloudbuild.yaml` file for the build configuration
3. Set up a trigger to deploy on commits to your main branch

```sh
# To manually trigger a build
gcloud builds submit --config cloudbuild.yaml
```
