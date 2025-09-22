# Notes Keeper

> A modern, Google Keep-inspired notes application with colorful notes, responsive design, and full CRUD functionality.

## 🚀 Quick Start

### Prerequisites
- Node.js (v14 or higher)
- MySQL Server
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd notes-keeper
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Database Setup**
   ```sql
   -- Run in MySQL
   CREATE DATABASE notes_db;
   USE notes_db;
   
   CREATE TABLE notes (
     id INT AUTO_INCREMENT PRIMARY KEY,
     title VARCHAR(255) NOT NULL,
     content TEXT NOT NULL,
     color VARCHAR(20) DEFAULT '#ffffff',
     created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   ```

4. **Configure Database Connection**
   Update `backend/server.js` with your MySQL credentials:
   ```javascript
   const db = mysql.createConnection({
     host: 'localhost',
     user: 'your_username',
     password: 'your_password',
     database: 'notes_db'
   });
   ```

5. **Start the Application**
   ```bash
   npm run dev
   ```

   This runs both frontend (port 3000) and backend (port 5002) concurrently.

## 🏗️ Architecture

### Tech Stack
- **Frontend**: React 19.1.1, CSS3
- **Backend**: Node.js, Express.js
- **Database**: MySQL
- **Development**: Concurrently, Nodemon

### Project Structure
```
notes-keeper/
├── backend/
│   ├── server.js          # Express server & API routes
│   ├── database.sql       # Database schema
│   └── package.json       # Backend dependencies
├── frontend/
│   ├── src/
│   │   ├── App.js         # Main React component
│   │   ├── App.css        # Styling
│   │   └── index.js       # React entry point
│   └── package.json       # Frontend dependencies
└── package.json           # Root package with dev scripts
```

## 🎨 Features

### Core Functionality
- ✅ **Create Notes**: Add notes with title and content
- ✅ **Edit Notes**: Modify existing notes inline
- ✅ **Delete Notes**: Remove notes with confirmation
- ✅ **Color Coding**: 12 predefined color themes
- ✅ **Responsive Design**: Mobile-first approach
- ✅ **Real-time Updates**: Instant UI updates

### UI/UX
- **Google Keep Style**: Clean, card-based interface
- **Masonry Grid**: Auto-adjusting responsive layout
- **Hover Effects**: Smooth animations and transitions
- **Color Picker**: Visual color selection
- **Mobile Optimized**: Touch-friendly interactions

## 🔌 API Reference

### Base URL
```
http://localhost:5002/api
```

### Endpoints

| Method | Endpoint | Description | Request Body |
|--------|----------|-------------|-------------|
| GET | `/notes` | Retrieve all notes | - |
| POST | `/notes` | Create new note | `{title, content, color}` |
| PUT | `/notes/:id` | Update existing note | `{title, content, color}` |
| DELETE | `/notes/:id` | Delete note | - |

### Response Format
```json
{
  "id": 1,
  "title": "Sample Note",
  "content": "Note content here",
  "color": "#ffeb3b",
  "created_at": "2024-01-01T00:00:00.000Z"
}
```

## 🎨 Color Palette

| Color | Hex Code | Usage |
|-------|----------|-------|
| Yellow | `#ffeb3b` | Default |
| Orange | `#ff9800` | Important |
| Red | `#f44336` | Urgent |
| Pink | `#e91e63` | Personal |
| Purple | `#9c27b0` | Creative |
| Deep Purple | `#673ab7` | Ideas |
| Indigo | `#3f51b5` | Work |
| Blue | `#2196f3` | Information |
| Light Blue | `#03a9f4` | Tasks |
| Cyan | `#00bcd4` | Projects |
| Teal | `#009688` | Goals |
| Green | `#4caf50` | Completed |

## 📱 Usage Guide

1. **Adding Notes**
   - Fill in title and content in the form
   - Select desired color from picker
   - Click "Add Note" to save

2. **Editing Notes**
   - Hover over any note card
   - Click the edit icon (✏️)
   - Modify content and click "Update Note"

3. **Deleting Notes**
   - Hover over any note card
   - Click the delete icon (🗑️)
   - Note is permanently removed

## 🛠️ Development

### Available Scripts

```bash
# Start both frontend and backend
npm run dev

# Start backend only
npm run server

# Start frontend only
npm run client

# Install all dependencies
npm install
```

### Development Workflow
1. Backend runs on `http://localhost:5002`
2. Frontend runs on `http://localhost:3000`
3. Hot reload enabled for both environments
4. CORS configured for cross-origin requests

## 🚀 Deployment

### Production Build
```bash
cd frontend
npm run build
```

### Environment Variables
Create `.env` files for production:
- Database credentials
- API endpoints
- Port configurations

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

## 📄 License

This project is licensed under the MIT License.

## 🐛 Known Issues

- Database connection requires manual configuration
- No user authentication implemented
- Limited to single-user environment

## 🔮 Future Enhancements

- [ ] User authentication & authorization
- [ ] Note sharing capabilities
- [ ] Search and filter functionality
- [ ] Rich text editor
- [ ] File attachments
- [ ] Categories and tags
- [ ] Dark mode theme