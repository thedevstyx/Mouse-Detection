# Mouse Movement User Identification System

A browser-based machine learning system that identifies users based on their mouse movement patterns. The system uses TensorFlow.js to train a neural network model that can distinguish between different users based on their unique mouse movement characteristics.

## Features

- Real-time mouse movement tracking
- User-specific data collection
- Neural network-based user identification
- Live confidence scoring
- Interactive training process
- Real-time user identification
- Responsive visualization of predictions

## How It Works

The system works in three main steps:

1. **Data Collection**
   - Records mouse movements for each user
   - Captures movement speed, position, and timing
   - Creates feature vectors from movement windows
   - Stores data separately for each registered user

2. **Model Training**
   - Processes collected movement data into training samples
   - Creates a neural network using TensorFlow.js
   - Trains the model using collected user data
   - Uses regularization and dropout for better generalization
   - Provides real-time training progress feedback

3. **User Identification**
   - Captures live mouse movements
   - Extracts movement features in real-time
   - Predicts user identity using the trained model
   - Displays confidence scores for all possible users
   - Updates predictions continuously during mouse movement

## Technical Details

### Neural Network Architecture
- Input layer: 4 features (average speed, max speed, average X, average Y)
- Hidden layers:
  - Dense layer (32 units, ReLU activation, L2 regularization)
  - Dropout layer (20% dropout rate)
  - Dense layer (16 units, ReLU activation, L2 regularization)
  - Dropout layer (20% dropout rate)
- Output layer: Softmax activation (number of units = number of users)

### Features Extracted
- Average movement speed
- Maximum movement speed
- Average X coordinate
- Average Y coordinate

### Training Parameters
- Epochs: 5000
- Batch size: 32
- Validation split: 20%
- Optimizer: Adam (learning rate: 0.001)
- Loss function: Categorical Cross-entropy

## Usage

1. **Setup**
   - Open `index.html` in a modern web browser
   - No server required - runs entirely in the browser
   - Requires WebGL support for TensorFlow.js

2. **Recording User Data**
   - Enter a username in the input field
   - Click "Start Recording" to begin collecting mouse movements
   - Move your mouse naturally around the screen
   - Click "Stop Recording" when finished
   - Repeat for at least 2 different users

3. **Training the Model**
   - Click "Train Neural Network Model" after collecting data
   - Wait for the training process to complete
   - Monitor training progress in real-time
   - Training is complete when accuracy stabilizes

4. **Identifying Users**
   - Click "Start Identification" to begin
   - Move the mouse naturally
   - View real-time predictions and confidence scores
   - Click "Stop Identification" to end the session

## Requirements

- Modern web browser with JavaScript enabled
- WebGL support
- TensorFlow.js (loaded automatically from CDN)

## Technical Requirements

- Browser with WebGL 2.0 support
- Sufficient GPU memory for model training
- Stable internet connection (for loading TensorFlow.js)

## Limitations

- Requires sufficient training data for accurate identification
- Performance depends on GPU capabilities
- Requires at least 2 users for training
- Best results with consistent mouse movement patterns

## Privacy Note

This system runs entirely in the browser. No data is sent to any server, and all processing happens locally on your device.

## License

MIT License - Feel free to use, modify, and distribute this code for any purpose. 