
# 🌟 Bucket List Tracker App

A full-stack bucket list tracker built using **React (Vite)** and **AWS Amplify**. Users can sign up, add, update, delete bucket list items, and optionally upload images. Deployed via AWS Amplify with CI/CD integration from GitHub.

---

## 🛠 Tech Stack

- **Frontend:** React + Vite
- **Backend:** AWS Amplify (Auth, Storage, Data)
- **Deployment:** AWS Amplify (CI/CD)
- **Authentication:** AWS Cognito
- **Storage:** AWS S3
- **Database:** AWS DynamoDB (via Amplify Data)

---

## 📦 Installation & Setup

### 1. Create React App with Vite

```bash
npm create vite@latest bucketlistapp -- --template react
cd bucketlistapp
npm install
npm run dev
```

### 2. Initialize GitHub Repository

```bash
git init
git add .
git commit -m "initial commit"
git remote add origin git@github.com:<your-username>/bucketlistapp.git
git branch -M main
git push -u origin main
```

---

## 🔧 AWS Amplify Setup

### 1. Scaffold Amplify

```bash
npm create amplify@latest -y
```

```bash
git add .
git commit -m "installing amplify"
git push origin main
```

### 2. Connect GitHub to AWS Amplify

- Go to [AWS Amplify Console](https://console.aws.amazon.com/amplify)
- Create new app → GitHub → Select repo and branch
- Create service role and use default settings
- Click **Save and Deploy**

---

## 🔐 Amplify Backend Configuration

### ✅ Authentication

- Email-based sign-up with verification.
- Defined in `amplify/auth/resource.ts`.

### 📚 Data (DynamoDB)

- Model defined in `amplify/data/resource.ts`
- Fields: `title`, `description`, `completed`
- Data is user-scoped (only owners can access their items)

### 🗂️ Storage (S3)

- Configured in `amplify/storage/resource.ts`
- User-specific image uploads

### 🔗 Backend Linkage

- `amplify/backend.ts` connects all resources (auth, data, storage)

---

## 🌩 Deploy Backend (Cloud Sandbox)

```bash
npx ampx sandbox
```

> ⚠️ If error:  
```bash
aws configure
```

Create IAM user in AWS → Generate **Access key** & **Secret access key** and provide them during `aws configure`.

---

## 🖼 Frontend + UI Setup

### 1. Install Amplify Libraries

```bash
npm install aws-amplify @aws-amplify/ui-react
```

### 2. Style UI

Edit `src/index.css` for responsive layout.

### 3. Update `App.jsx`

Include Amplify components for:
- Authentication (sign-up, sign-in)
- CRUD operations for bucket list items
- File upload for images

---

## 🧪 Local Testing

```bash
npm run dev
```

- Sign up using email → verify via code
- Add / update / delete items
- Upload images (if implemented)

---

## ☁️ Push to GitHub & Deploy

```bash
git add .
git commit -m "bucket list tracker app"
git push origin main
```

- AWS Amplify auto-builds and deploys your app.
- Visit the hosted app URL from Amplify Console.

---

## 📸 Features

- ✅ User authentication (sign-up, sign-in, email verification)
- ✅ Add/edit/delete bucket list items
- ✅ Upload images (optional)
- ✅ Deployed with AWS Amplify + CI/CD from GitHub

---

## 📁 Folder Structure

```
bucketlistapp/
├── amplify/
│   ├── auth/
│   ├── data/
│   ├── storage/
│   └── backend.ts
├── public/
├── src/
│   ├── App.jsx
│   ├── index.css
│   └── main.jsx
├── package.json
└── README.md
```

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first.

---

## 📜 License

MIT
