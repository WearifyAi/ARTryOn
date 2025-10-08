# AR Try-On Application

A web-based Augmented Reality (AR) try-on application that allows users to virtually try on various accessories and items using DeepAR technology. The application supports multiple AR effects including watches, shoes, bags, bracelets, and other fashion accessories.

## 🚀 Features

- **Real-time AR Try-On**: Experience virtual try-on of various accessories in real-time
- **Multiple Product Categories**: 
  - Watches (Apple Watch, Omega, various watch models)
  - Shoes (Sneakers, heels, various shoe styles)
  - Bags (Handbags, backpacks, luxury bags)
  - Bracelets and Jewelry
  - Caps and Accessories
- **Camera Controls**: Switch between front and rear cameras
- **Firebase Integration**: Analytics and usage tracking
- **Responsive Design**: Works on various device sizes

## 🛠️ Technology Stack

- **DeepAR SDK**: AR engine for real-time face tracking and 3D rendering
- **Firebase**: Backend services for analytics and data storage
- **Vanilla JavaScript**: Core application logic
- **HTML5**: Web interface
- **WebRTC**: Camera access and video streaming

## 📁 Project Structure

```
ARTryOn/
├── effects/                 # DeepAR effect files (.deepar)
│   ├── watches/            # Watch-related AR effects
│   ├── shoes/              # Shoe-related AR effects
│   ├── bags/               # Bag-related AR effects
│   ├── jewelry/            # Jewelry and bracelet effects
│   └── accessories/         # Other accessory effects
├── index.html              # Main application file
└── README.md               # Project documentation
```

## 🚀 Getting Started

### Prerequisites

- Modern web browser with WebRTC support
- HTTPS connection (required for camera access)
- DeepAR license key

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd ARTryOn
   ```

2. **Set up a local server**
   Since the application requires HTTPS for camera access, you'll need to serve it through a secure connection:
   
   **Option 1: Using Python**
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Then access via https://localhost:8000
   ```
   
   **Option 2: Using Node.js (http-server with SSL)**
   ```bash
   npm install -g http-server
   http-server -S -C cert.pem -K key.pem
   ```

3. **Configure Firebase** (Optional)
   - Update the Firebase configuration in `index.html` with your project credentials
   - Ensure your Firebase project has Realtime Database enabled

### Usage

1. **Open the application** in your browser
2. **Allow camera permissions** when prompted
3. **Use URL parameters** to specify which effect to load:
   ```
   https://your-domain.com/?effect=watch&camera=front
   https://your-domain.com/?effect=shoes&camera=back
   ```

### URL Parameters

- `effect`: Name of the DeepAR effect file (without .deepar extension)
- `camera`: Camera orientation (`front` for selfie camera, `back` for rear camera)
- `cl`: Category label for analytics (optional, defaults to 'pregomesh')

## 🎯 Available Effects

### Watches
- `apple_watch_ultra` - Apple Watch Ultra
- `omega` - Omega watch
- `AzatMardwatch` - Azat Mard watch
- `Watch` - Generic watch
- `watchglb` - 3D watch model

### Shoes
- `sneaker` - Sneaker try-on
- `heels` - High heels
- `shoes` - Generic shoes
- `newSneakers` - New sneaker model
- `balenciaga` - Balenciaga shoes

### Bags
- `bag` - Handbag
- `bagD` - Designer bag
- `bagfinal` - Final bag design
- `balenciaga` - Balenciaga bag

### Jewelry & Accessories
- `BrasletGoldEffect` - Gold bracelet
- `BrasletNoEffect` - Plain bracelet
- `OmegaBracelet` - Omega bracelet
- `F1Cap` - F1 racing cap
- `aviators` - Aviator sunglasses

## 🔧 Configuration

### DeepAR License
Update the license key in `index.html`:
```javascript
licenseKey: 'your-deepar-license-key-here'
```

### Firebase Configuration
Update the Firebase config object with your project details:
```javascript
const firebaseConfig = {
    apiKey: "your-api-key",
    authDomain: "your-project.firebaseapp.com",
    databaseURL: "https://your-project.firebaseio.com",
    projectId: "your-project-id",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "your-sender-id",
    appId: "your-app-id"
};
```

## 📱 Browser Compatibility

- **Chrome**: 80+ (Recommended)
- **Firefox**: 75+
- **Safari**: 13+
- **Edge**: 80+

## 🔒 Security Notes

- The application requires HTTPS for camera access
- Firebase credentials are exposed in the client-side code
- Consider implementing server-side proxy for production deployments

## 📊 Analytics

The application tracks usage analytics through Firebase Realtime Database:
- Effect usage frequency
- Timestamp tracking
- Category-based analytics

## 🚀 Deployment

### Static Hosting
Deploy to any static hosting service:
- **Netlify**: Drag and drop the project folder
- **Vercel**: Connect your GitHub repository
- **Firebase Hosting**: Use Firebase CLI

### Server Requirements
- HTTPS enabled
- Support for ES6 modules
- WebRTC support

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Troubleshooting

### Common Issues

1. **Camera not working**
   - Ensure HTTPS connection
   - Check browser permissions
   - Verify WebRTC support

2. **Effects not loading**
   - Check effect file paths
   - Verify DeepAR license key
   - Ensure effect files are accessible

3. **Firebase errors**
   - Verify Firebase configuration
   - Check database rules
   - Ensure proper authentication

### Support

For support and questions:
- Check the [DeepAR Documentation](https://docs.deepar.io/)
- Review browser console for error messages
- Ensure all dependencies are properly loaded

## 🔮 Future Enhancements

- [ ] User authentication system
- [ ] Product catalog integration
- [ ] Social sharing features
- [ ] Mobile app development
- [ ] Advanced analytics dashboard
- [ ] Multi-language support

---

**Note**: This application requires a valid DeepAR license for production use. Ensure you have the proper licensing before deploying to production environments.
