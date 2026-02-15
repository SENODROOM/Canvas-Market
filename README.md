# Canvas Market

A comprehensive marketplace platform for canvas products, built with modern web technologies to provide a seamless buying and selling experience for artists, creators, and canvas enthusiasts.

## 📋 Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Sub-Repositories](#sub-repositories)
  - [Frontend Repository](#frontend-repository)
  - [Backend Repository](#backend-repository)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
  - [Contributing to Frontend](#contributing-to-frontend)
  - [Contributing to Backend](#contributing-to-backend)
- [Development Workflow](#development-workflow)
- [Code of Conduct](#code-of-conduct)
- [License](#license)
- [Contact](#contact)

## 🎨 Overview

Canvas Market is a full-stack marketplace application designed to connect canvas artists with buyers. The platform provides features for listing, browsing, purchasing, and managing canvas artworks and products. Built with scalability and user experience in mind, Canvas Market leverages modern technologies to deliver a robust and efficient platform.

### Key Features

- **User Authentication & Authorization**: Secure user registration and login system
- **Product Listings**: Browse and search through various canvas products
- **Shopping Cart**: Add items to cart and manage orders
- **Payment Integration**: Secure payment processing
- **Seller Dashboard**: Manage products, orders, and analytics
- **Responsive Design**: Optimized for desktop, tablet, and mobile devices
- **Admin Panel**: Comprehensive admin tools for platform management

## 🏗️ Architecture

Canvas Market follows a microservices architecture with separate frontend and backend repositories:

```
Canvas-Market/
├── frontend/          # React-based user interface
├── backend/           # Node.js/Express API server
└── docs/              # Documentation and guides
```

## 📁 Sub-Repositories

### Frontend Repository

**Technology Stack:**
- React.js / Next.js
- State Management (Redux/Context API)
- Styling (Tailwind CSS / Styled Components)
- TypeScript
- Testing (Jest, React Testing Library)

**Key Responsibilities:**
- User interface and user experience
- Client-side routing and navigation
- State management
- API integration
- Form validation and error handling

[📖 Frontend Documentation](./frontend/README.md) | [🐛 Frontend Issues](./frontend/issues)

### Backend Repository

**Technology Stack:**
- Node.js with Express.js / Django / FastAPI
- Database (PostgreSQL / MongoDB)
- Authentication (JWT / OAuth)
- Payment Processing (Stripe / PayPal)
- File Storage (AWS S3 / Cloudinary)
- Testing (Mocha/Chai or PyTest)

**Key Responsibilities:**
- RESTful API endpoints
- Database management and migrations
- Authentication and authorization
- Business logic implementation
- File upload and management
- Payment processing

[📖 Backend Documentation](./backend/README.md) | [🐛 Backend Issues](./backend/issues)

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:
- Node.js (v16 or higher)
- npm or yarn
- Git
- Database (PostgreSQL/MongoDB)
- Docker (optional, for containerized development)

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/SENODROOM/Canvas-Market.git
   cd Canvas-Market
   ```

2. **Install dependencies**
   ```bash
   # Frontend
   cd frontend
   npm install
   
   # Backend
   cd ../backend
   npm install
   ```

3. **Set up environment variables**
   ```bash
   # Frontend
   cp frontend/.env.example frontend/.env.local
   
   # Backend
   cp backend/.env.example backend/.env
   ```

4. **Start development servers**
   ```bash
   # Frontend (in one terminal)
   cd frontend
   npm run dev
   
   # Backend (in another terminal)
   cd backend
   npm run dev
   ```

5. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000

## 🤝 Contributing

We welcome contributions from the community! Whether you're fixing bugs, adding new features, improving documentation, or suggesting enhancements, your help is appreciated.

### How to Contribute

1. **Fork the repository**
   - Click the "Fork" button at the top right of this page

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/Canvas-Market.git
   cd Canvas-Market
   ```

3. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   # or for bug fixes
   git checkout -b fix/bug-description
   ```

4. **Make your changes**
   - Write clean, maintainable code
   - Follow the project's coding standards
   - Add tests for new features
   - Update documentation as needed

5. **Commit your changes**
   ```bash
   git add .
   git commit -m "feat: add new feature description"
   ```
   
   **Commit Message Convention:**
   - `feat:` for new features
   - `fix:` for bug fixes
   - `docs:` for documentation changes
   - `style:` for formatting changes
   - `refactor:` for code refactoring
   - `test:` for adding tests
   - `chore:` for maintenance tasks

6. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

7. **Create a Pull Request**
   - Go to the original repository
   - Click "New Pull Request"
   - Select your fork and branch
   - Fill out the PR template with details about your changes

### Contribution Guidelines

- **Code Quality**: Ensure your code passes all linting and testing checks
- **Documentation**: Update relevant documentation for any new features
- **Testing**: Add unit and integration tests for new functionality
- **Responsiveness**: Ensure UI changes work across different screen sizes
- **Accessibility**: Follow WCAG guidelines for accessible web development
- **Performance**: Consider the performance impact of your changes

---

## 🎨 Contributing to Frontend

The frontend is the face of Canvas Market. Here's how you can contribute to making it better.

### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

### Frontend Project Structure

```
frontend/
├── public/              # Static assets
├── src/
│   ├── components/      # Reusable UI components
│   ├── pages/           # Page components
│   ├── hooks/           # Custom React hooks
│   ├── utils/           # Utility functions
│   ├── services/        # API service layer
│   ├── store/           # State management
│   ├── styles/          # Global styles and themes
│   ├── types/           # TypeScript type definitions
│   └── App.tsx          # Main application component
├── tests/               # Test files
└── package.json
```

### Frontend Coding Standards

#### Component Guidelines

1. **Use Functional Components**: Prefer functional components with hooks over class components
   
   ```tsx
   // Good
   const ProductCard: React.FC<ProductCardProps> = ({ product }) => {
     const [isLiked, setIsLiked] = useState(false);
     
     return (
       <div className="product-card">
         {/* Component JSX */}
       </div>
     );
   };
   ```

2. **Component File Structure**: One component per file, with clear naming conventions
   ```
   components/
   ├── ProductCard/
   │   ├── ProductCard.tsx
   │   ├── ProductCard.test.tsx
   │   ├── ProductCard.module.css
   │   └── index.ts
   ```

3. **Props Typing**: Always define TypeScript interfaces for props
   ```tsx
   interface ProductCardProps {
     product: Product;
     onAddToCart: (id: string) => void;
     className?: string;
   }
   ```

#### Styling Guidelines

- Use CSS Modules or styled-components for component-specific styles
- Follow BEM naming convention for CSS classes
- Maintain consistent spacing and typography using design tokens
- Ensure mobile-first responsive design

#### State Management

- Use Context API for global state that doesn't change frequently
- Use Redux/Zustand for complex state management
- Keep state as local as possible
- Avoid prop drilling beyond 2-3 levels

#### API Integration

```tsx
// Use custom hooks for API calls
const useProducts = () => {
  const [products, setProducts] = useState<Product[]>([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState<Error | null>(null);

  useEffect(() => {
    fetchProducts()
      .then(setProducts)
      .catch(setError)
      .finally(() => setLoading(false));
  }, []);

  return { products, loading, error };
};
```

### Frontend Testing

```bash
# Run all tests
npm test

# Run tests in watch mode
npm test -- --watch

# Generate coverage report
npm test -- --coverage
```

**Testing Requirements:**
- Write unit tests for utility functions
- Write component tests for UI components
- Write integration tests for user flows
- Aim for >80% code coverage

**Example Test:**
```tsx
import { render, screen, fireEvent } from '@testing-library/react';
import ProductCard from './ProductCard';

describe('ProductCard', () => {
  it('renders product information correctly', () => {
    const product = { id: '1', name: 'Canvas Art', price: 29.99 };
    render(<ProductCard product={product} onAddToCart={jest.fn()} />);
    
    expect(screen.getByText('Canvas Art')).toBeInTheDocument();
    expect(screen.getByText('$29.99')).toBeInTheDocument();
  });

  it('calls onAddToCart when button is clicked', () => {
    const onAddToCart = jest.fn();
    const product = { id: '1', name: 'Canvas Art', price: 29.99 };
    render(<ProductCard product={product} onAddToCart={onAddToCart} />);
    
    fireEvent.click(screen.getByRole('button', { name: /add to cart/i }));
    expect(onAddToCart).toHaveBeenCalledWith('1');
  });
});
```

### Frontend-Specific Issues

We especially welcome contributions in these areas:

- **UI/UX Improvements**: Better user interfaces and experiences
- **Accessibility**: Making the platform accessible to all users
- **Performance**: Optimizing load times and rendering
- **Mobile Responsiveness**: Improving mobile user experience
- **Internationalization**: Adding multi-language support
- **Dark Mode**: Implementing theme switching

### Submitting Frontend Pull Requests

When submitting a PR for frontend changes:

1. Include screenshots or GIFs of UI changes
2. Test on multiple browsers (Chrome, Firefox, Safari, Edge)
3. Verify responsive design on different screen sizes
4. Check accessibility with screen readers
5. Ensure no console errors or warnings
6. Update Storybook stories if applicable

---

## ⚙️ Contributing to Backend

The backend powers Canvas Market with robust APIs and business logic. Here's how to contribute.

### Backend Setup

```bash
cd backend
npm install

# Set up database
npm run db:setup
npm run db:migrate

# Start development server
npm run dev
```

### Backend Project Structure

```
backend/
├── src/
│   ├── controllers/     # Request handlers
│   ├── models/          # Database models
│   ├── routes/          # API routes
│   ├── middleware/      # Custom middleware
│   ├── services/        # Business logic
│   ├── utils/           # Utility functions
│   ├── validators/      # Request validation schemas
│   ├── config/          # Configuration files
│   └── app.ts           # Application entry point
├── tests/               # Test files
├── migrations/          # Database migrations
└── package.json
```

### Backend Coding Standards

#### API Design

1. **RESTful Principles**: Follow REST conventions for API design
   ```
   GET    /api/products        # Get all products
   GET    /api/products/:id    # Get single product
   POST   /api/products        # Create product
   PUT    /api/products/:id    # Update product
   DELETE /api/products/:id    # Delete product
   ```

2. **Consistent Response Format**:
   ```javascript
   // Success response
   {
     "success": true,
     "data": { /* response data */ },
     "message": "Operation successful"
   }

   // Error response
   {
     "success": false,
     "error": {
       "code": "VALIDATION_ERROR",
       "message": "Invalid input data",
       "details": [/* validation errors */]
     }
   }
   ```

3. **Status Codes**: Use appropriate HTTP status codes
   - `200` OK - Successful GET, PUT, PATCH
   - `201` Created - Successful POST
   - `204` No Content - Successful DELETE
   - `400` Bad Request - Validation error
   - `401` Unauthorized - Authentication required
   - `403` Forbidden - Insufficient permissions
   - `404` Not Found - Resource not found
   - `500` Internal Server Error - Server error

#### Controller Pattern

```javascript
// controllers/productController.js
const Product = require('../models/Product');
const { asyncHandler } = require('../middleware/async');

exports.getProducts = asyncHandler(async (req, res) => {
  const { page = 1, limit = 10, search } = req.query;
  
  const query = search 
    ? { name: { $regex: search, $options: 'i' } }
    : {};
  
  const products = await Product.find(query)
    .limit(limit * 1)
    .skip((page - 1) * limit)
    .sort({ createdAt: -1 });
  
  const count = await Product.countDocuments(query);
  
  res.status(200).json({
    success: true,
    data: products,
    pagination: {
      page: Number(page),
      limit: Number(limit),
      total: count,
      pages: Math.ceil(count / limit)
    }
  });
});

exports.createProduct = asyncHandler(async (req, res) => {
  const product = await Product.create({
    ...req.body,
    seller: req.user.id
  });
  
  res.status(201).json({
    success: true,
    data: product,
    message: 'Product created successfully'
  });
});
```

#### Database Models

```javascript
// models/Product.js
const mongoose = require('mongoose');

const ProductSchema = new mongoose.Schema({
  name: {
    type: String,
    required: [true, 'Product name is required'],
    trim: true,
    maxlength: [100, 'Name cannot exceed 100 characters']
  },
  description: {
    type: String,
    required: [true, 'Description is required'],
    maxlength: [2000, 'Description cannot exceed 2000 characters']
  },
  price: {
    type: Number,
    required: [true, 'Price is required'],
    min: [0, 'Price cannot be negative']
  },
  images: [{
    url: String,
    publicId: String
  }],
  seller: {
    type: mongoose.Schema.ObjectId,
    ref: 'User',
    required: true
  },
  category: {
    type: String,
    required: [true, 'Category is required'],
    enum: ['Canvas Art', 'Canvas Print', 'Canvas Board', 'Other']
  },
  stock: {
    type: Number,
    required: true,
    default: 0
  },
  isActive: {
    type: Boolean,
    default: true
  }
}, {
  timestamps: true,
  toJSON: { virtuals: true },
  toObject: { virtuals: true }
});

// Indexes for better query performance
ProductSchema.index({ name: 'text', description: 'text' });
ProductSchema.index({ seller: 1, createdAt: -1 });
ProductSchema.index({ category: 1, price: 1 });

module.exports = mongoose.model('Product', ProductSchema);
```

#### Middleware

```javascript
// middleware/auth.js
const jwt = require('jsonwebtoken');
const User = require('../models/User');

exports.protect = asyncHandler(async (req, res, next) => {
  let token;
  
  if (req.headers.authorization?.startsWith('Bearer')) {
    token = req.headers.authorization.split(' ')[1];
  }
  
  if (!token) {
    return res.status(401).json({
      success: false,
      error: { message: 'Not authorized to access this route' }
    });
  }
  
  try {
    const decoded = jwt.verify(token, process.env.JWT_SECRET);
    req.user = await User.findById(decoded.id);
    next();
  } catch (error) {
    return res.status(401).json({
      success: false,
      error: { message: 'Invalid token' }
    });
  }
});
```

#### Input Validation

```javascript
// validators/productValidator.js
const Joi = require('joi');

exports.createProductSchema = Joi.object({
  name: Joi.string().trim().max(100).required(),
  description: Joi.string().trim().max(2000).required(),
  price: Joi.number().min(0).required(),
  category: Joi.string().valid('Canvas Art', 'Canvas Print', 'Canvas Board', 'Other').required(),
  stock: Joi.number().integer().min(0).default(0),
  images: Joi.array().items(
    Joi.object({
      url: Joi.string().uri().required(),
      publicId: Joi.string().required()
    })
  ).max(10)
});

// middleware/validate.js
exports.validate = (schema) => {
  return (req, res, next) => {
    const { error } = schema.validate(req.body, { abortEarly: false });
    
    if (error) {
      return res.status(400).json({
        success: false,
        error: {
          code: 'VALIDATION_ERROR',
          message: 'Validation failed',
          details: error.details.map(detail => ({
            field: detail.path.join('.'),
            message: detail.message
          }))
        }
      });
    }
    
    next();
  };
};
```

### Backend Testing

```bash
# Run all tests
npm test

# Run tests with coverage
npm run test:coverage

# Run integration tests
npm run test:integration

# Run specific test file
npm test -- tests/product.test.js
```

**Testing Requirements:**
- Write unit tests for services and utilities
- Write integration tests for API endpoints
- Mock external dependencies
- Test error handling scenarios
- Aim for >80% code coverage

**Example Test:**
```javascript
// tests/product.test.js
const request = require('supertest');
const app = require('../src/app');
const Product = require('../src/models/Product');

describe('Product API', () => {
  beforeEach(async () => {
    await Product.deleteMany({});
  });

  describe('GET /api/products', () => {
    it('should return all products', async () => {
      await Product.create([
        { name: 'Product 1', price: 29.99, description: 'Test product' },
        { name: 'Product 2', price: 39.99, description: 'Test product' }
      ]);

      const res = await request(app)
        .get('/api/products')
        .expect(200);

      expect(res.body.success).toBe(true);
      expect(res.body.data).toHaveLength(2);
    });

    it('should filter products by search query', async () => {
      await Product.create([
        { name: 'Canvas Art', price: 29.99, description: 'Beautiful art' },
        { name: 'Canvas Print', price: 39.99, description: 'Quality print' }
      ]);

      const res = await request(app)
        .get('/api/products?search=art')
        .expect(200);

      expect(res.body.data).toHaveLength(1);
      expect(res.body.data[0].name).toBe('Canvas Art');
    });
  });

  describe('POST /api/products', () => {
    it('should create a new product with valid data', async () => {
      const productData = {
        name: 'New Canvas',
        description: 'A beautiful canvas',
        price: 49.99,
        category: 'Canvas Art',
        stock: 10
      };

      const res = await request(app)
        .post('/api/products')
        .set('Authorization', `Bearer ${authToken}`)
        .send(productData)
        .expect(201);

      expect(res.body.success).toBe(true);
      expect(res.body.data.name).toBe(productData.name);
    });

    it('should return 400 for invalid data', async () => {
      const res = await request(app)
        .post('/api/products')
        .set('Authorization', `Bearer ${authToken}`)
        .send({ name: 'Invalid' })
        .expect(400);

      expect(res.body.success).toBe(false);
      expect(res.body.error.code).toBe('VALIDATION_ERROR');
    });
  });
});
```

### Database Migrations

```javascript
// migrations/20240215_add_featured_to_products.js
exports.up = async function(db) {
  await db.collection('products').updateMany(
    {},
    { $set: { isFeatured: false } }
  );
  
  await db.collection('products').createIndex({ isFeatured: 1 });
};

exports.down = async function(db) {
  await db.collection('products').updateMany(
    {},
    { $unset: { isFeatured: "" } }
  );
  
  await db.collection('products').dropIndex('isFeatured_1');
};
```

### Backend-Specific Issues

We especially welcome contributions in these areas:

- **API Endpoints**: Adding new endpoints or improving existing ones
- **Performance**: Database query optimization and caching
- **Security**: Enhancing authentication and authorization
- **Payment Integration**: Improving payment processing
- **Email Services**: Template improvements and delivery optimization
- **File Upload**: Enhancing image processing and storage
- **Error Handling**: Better error messages and logging

### Submitting Backend Pull Requests

When submitting a PR for backend changes:

1. Include API documentation updates
2. Add/update integration tests
3. Document any new environment variables
4. Update database migration files if needed
5. Ensure backward compatibility
6. Check for security vulnerabilities
7. Verify performance impact

---

## 🔄 Development Workflow

### Branch Naming Convention

- `feature/feature-name` - For new features
- `fix/bug-description` - For bug fixes
- `refactor/component-name` - For code refactoring
- `docs/update-description` - For documentation
- `test/test-description` - For adding tests

### Pull Request Process

1. **Create descriptive PR title**: Use conventional commit format
   - ✨ feat: Add user profile page
   - 🐛 fix: Fix cart calculation bug
   - 📝 docs: Update API documentation
   - ♻️ refactor: Improve database queries

2. **Fill out PR template**: Provide context and testing details

3. **Link related issues**: Reference issues using keywords like "Closes #123"

4. **Request reviews**: Tag relevant maintainers

5. **Address feedback**: Respond to all review comments

6. **Wait for approval**: At least one approval required before merging

### Code Review Guidelines

**For Contributors:**
- Be open to feedback and constructive criticism
- Respond promptly to review comments
- Make requested changes in separate commits
- Re-request review after making changes

**For Reviewers:**
- Be respectful and constructive
- Focus on code quality, not coding style preferences
- Test the changes locally when possible
- Approve when code meets standards

### Continuous Integration

All pull requests must pass:
- ✅ Linting checks
- ✅ Unit tests
- ✅ Integration tests
- ✅ Build process
- ✅ Code coverage threshold (80%+)

## 📋 Code of Conduct

We are committed to providing a welcoming and inclusive environment for all contributors. Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md).

### Our Standards

**Expected Behavior:**
- Use welcoming and inclusive language
- Be respectful of differing viewpoints
- Accept constructive criticism gracefully
- Focus on what's best for the community
- Show empathy towards other community members

**Unacceptable Behavior:**
- Harassment or discriminatory comments
- Personal attacks or insults
- Publishing others' private information
- Trolling or inflammatory comments
- Other unprofessional conduct

### Reporting Issues

If you experience or witness unacceptable behavior, please report it to [conduct@canvasmarket.com](mailto:conduct@canvasmarket.com).

## 🐛 Bug Reports

When filing a bug report, please include:

1. **Clear title**: Describe the bug in one sentence
2. **Description**: Detailed explanation of the issue
3. **Steps to reproduce**: Step-by-step instructions
4. **Expected behavior**: What should happen
5. **Actual behavior**: What actually happens
6. **Screenshots**: If applicable
7. **Environment**:
   - Browser/OS version
   - Node.js version
   - Relevant package versions

**Bug Report Template:**
```markdown
**Bug Description**
A clear description of what the bug is.

**To Reproduce**
1. Go to '...'
2. Click on '....'
3. Scroll down to '....'
4. See error

**Expected Behavior**
A clear description of what you expected to happen.

**Screenshots**
If applicable, add screenshots to help explain your problem.

**Environment:**
 - OS: [e.g. iOS]
 - Browser: [e.g. chrome, safari]
 - Version: [e.g. 22]
```

## 💡 Feature Requests

We welcome feature suggestions! When requesting a feature:

1. **Check existing issues**: Avoid duplicates
2. **Describe the feature**: What should it do?
3. **Explain the use case**: Why is it needed?
4. **Provide examples**: How would it work?
5. **Consider alternatives**: Any other approaches?

## 📚 Documentation

Good documentation is crucial. When contributing:

- Update README for new features
- Add inline code comments for complex logic
- Update API documentation for endpoint changes
- Create/update user guides when needed
- Include JSDoc comments for functions

## 🎯 Areas Needing Contribution

We especially need help with:

### High Priority
- 🔐 Security auditing and improvements
- ♿ Accessibility enhancements
- 🌍 Internationalization (i18n)
- 📱 Mobile app development
- 📊 Analytics and reporting features

### Medium Priority
- 🎨 UI/UX improvements
- ⚡ Performance optimization
- 🧪 Test coverage expansion
- 📖 Documentation improvements
- 🐛 Bug fixes

### Nice to Have
- 🌙 Dark mode implementation
- 🔔 Push notifications
- 💬 Real-time chat support
- 📧 Email template design
- 🎬 Tutorial videos

## 🏆 Recognition

We value all contributions! Contributors will be:
- Listed in our [CONTRIBUTORS.md](CONTRIBUTORS.md) file
- Mentioned in release notes for significant contributions
- Given credit in commit history
- Invited to join our Discord community

## 📜 License

By contributing to Canvas Market, you agree that your contributions will be licensed under the [MIT License](LICENSE).

## 📞 Contact & Support

- **General Questions**: Open a [GitHub Discussion](https://github.com/SENODROOM/Canvas-Market/discussions)
- **Bug Reports**: Create an [Issue](https://github.com/SENODROOM/Canvas-Market/issues)
- **Security Issues**: Email security@canvasmarket.com
- **Discord Community**: [Join our server](https://discord.gg/canvasmarket)
- **Twitter**: [@CanvasMarket](https://twitter.com/canvasmarket)

## 🙏 Thank You!

Thank you for considering contributing to Canvas Market! Your efforts help make this platform better for everyone. We look forward to your contributions!

---

**Happy Coding! 🎨✨**

*Made with ❤️ by the Canvas Market community*
