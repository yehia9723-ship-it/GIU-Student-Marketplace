# GIU Student Marketplace

**Course:** Electronic Business Development (BINF 503) · Winter 2026  
**Instructor:** Dr. Nourhan Hamdi  
**Teaching Assistants:** Mr. Nour Gaser, Mr. Omar Alaa, Ms. Mariam Khalid, Mr. Younes Zied, Mr. Mahmoud Hani

## 1. Team

| Name | Student ID | Tutorial group | GitHub username |
|---|---|---|---|
| Yehia Hossam | 16007348 | T3 | Yehia9723-ship-it |
| Abdelrahman Khaled | 16002772 | T1 | abdelrahmankhaledhemeda |

## 2. The idea

GIU Student Marketplace is a web application where university students can buy and sell used items. Students can create accounts, post items they want to sell, and browse products posted by other students. The application makes it easier for students to find affordable university supplies and sell items they no longer need.

## 3. Features

### 3.1 The full product

- Student registration and login.
- Create and manage student accounts.
- View available products.
- Create product listings.
- Edit and delete personal listings.
- View product details.
- Search for products.
- Filter products by category.
- Send purchase requests.
- Accept or reject purchase requests.
- View sent and received purchase requests.

### 3.2 The use cases we will build

| # | Use case | What the user does | What they see | What is stored |
|---|---|---|---|---|
| 1 | Registration and login | Registers using their name, email and password, and logs in using their account details | Their home page with their name displayed | A User with a hashed password |
| 2 | Manage product listings | Creates a product listing with a title, description and price; views, edits and deletes their own listings | Their published products and updated listing information | A Listing containing product details and seller ID |

## 4. Who owns what

| Member | Use case |
|---|---|
| Yehia Hossam | 1. Registration and login |
| Abdelrahman Khaled | 2. Manage product listings |

## 5. Data model


## 5. Data model

### User

```javascript
const userSchema = new mongoose.Schema({
  name: { type: String, required: true },
  email: { type: String, required: true, unique: true },
  password: { type: String, required: true }
});
```

### Listing

```javascript
const listingSchema = new mongoose.Schema({
  title: { type: String, required: true },
  description: { type: String, required: true },
  price: { type: Number, required: true },
  seller: {
    type: mongoose.Schema.Types.ObjectId,
    ref: "User",
    required: true
  }
}, { timestamps: true });
```

```

## 6. Run it locally

### Back end

```bash
cd backend
npm install
# create backend/.env from backend/.env.example (see the table below)
npm start
```

The API runs on [http://localhost:3000](http://localhost:3000).

| Variable in `.env` | What it is |
|---|---|
| `MONGODB_URI` | The connection string of your MongoDB Atlas database |
| `JWT_SECRET` | Any long random text, used to sign login tokens |
| [Any other variable] | [What it is] |

### Front end

```bash
cd frontend
npm install
npm run dev
```

The app runs on [the address `npm run dev` prints, e.g. [http://localhost:5173](http://localhost:5173)].