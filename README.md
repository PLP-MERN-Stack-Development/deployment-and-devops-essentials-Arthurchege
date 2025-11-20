# Real-Time Chat Application: Deployment and DevOps (Week 7 Submission)

This project implements a **real-time chat application** using **React** (Vite), **Node.js/Express**, and **Socket.io**. It has been successfully deployed to production using Continuous Deployment (CD) and includes foundational DevOps practices as required for the Week 7 assignment.

The application demonstrates full **bidirectional communication** and client-side logic ready for robust authentication and persistence.

---

## 🏗️ Project Structure

The project uses a standard monorepo structure:

---

## 🚀 Features Implemented & Verified

| Requirement Area              | Status       | Feature Implemented                                                                                                                        |
| :---------------------------- | :----------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| **Task 1 & 2: Core Chat**     | **Complete** | **Global Chat** is functional (verified live). **Username Auth** and **Online Status** list are working.                                   |
| **Task 3: Advanced Features** | **Complete** | **Typing Indicator** and **Private Messaging** logic (server-side) are included.                                                           |
| **Task 4: CI/CD Pipeline**    | **Complete** | **GitHub Actions** pipeline setup (`frontend-cd.yml`) is configured to automatically build and deploy the client to Netlify on every push. |
| **Deployment Fixes**          | **Resolved** | **CORS Policy** error resolved by setting **`CLIENT_URL`** on the Render backend.                                                          |

---

## 🌐 Deployed Application URLs

| Component                | Platform    | Live URL                                                           |
| :----------------------- | :---------- | :----------------------------------------------------------------- |
| **Frontend (Client)**    | **Netlify** | `https://wk7.netlify.app`                                          |
| **Backend (Server/API)** | **Render**  | `https://real-time-communication-with-socket-io-990a.onrender.com` |

---

## 🔑 Environment Configuration

The following variables are required for the live deployment:

| Variable               | Location Set                     | Value                                                              | Purpose                                                                      |
| :--------------------- | :------------------------------- | :----------------------------------------------------------------- | :--------------------------------------------------------------------------- |
| **`CLIENT_URL`**       | **Render Dashboard (Secret)**    | `https://wk7.netlify.app`                                          | **Fixes CORS** by telling the server which frontend origin to trust.         |
| **`JWT_SECRET`**       | **Render Dashboard (Secret)**    | _\[Long, random generated string]_                                 | Used for secure authentication and token signing.                            |
| **`VITE_BACKEND_URL`** | **Netlify Dashboard (Variable)** | `https://real-time-communication-with-socket-io-990a.onrender.com` | Directs the client's Socket.io connection and API calls to the live backend. |

---

## 🛡️ Task 5: Monitoring and Maintenance Documentation

### A. Application Health Check (Task 5a)

The backend exposes a basic health check endpoint that monitoring services can poll:

- **Endpoint:** `GET /`
- **Status:** Returns **200 OK** with the body text "Socket.io Chat Server is running".
- **Purpose:** Ensures the Express server process is active and running on Render.

### B. Deployment Rollback Procedure (Task 5c)

In case of a deployment failure on the `main` branch, the rollback procedures are documented below:

| Platform               | Rollback Procedure                                                                                                                                                                          |
| :--------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Frontend (Netlify)** | Navigate to the **Deploys** tab in the Netlify dashboard, select the previous successful deploy in the history list, and click **"Publish deploy"** to revert to the older build instantly. |
| **Backend (Render)**   | Navigate to the **Deploys** tab in the Render dashboard, select the previous successful commit in the deployment history, and click **"Re-deploy previous commit."**                        |

### C. Maintenance Plan

- **Database:** Schedule weekly automated backups of the MongoDB Atlas cluster.
- **Server Updates:** Plan quarterly updates for Node.js and major dependency versions.
- **Logging:** Configure Render/external logging (e.g., Sentry) to capture errors in production for continuous maintenance.

---

## 📸 Screenshots and Verification

                                |

| **Online Status & Bidirectional Chat**
(Screenshot1.png)

| **Typing Indicator Proof**  
 (Screenshot2.png)

| **CI/CD Success** |
(Screenshot3.png)
