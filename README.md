# Mouse Movement User Identification System

A browser-based machine learning system that identifies users based on their mouse movement patterns. The system uses TensorFlow.js to train a neural network model that can distinguish between different users based on their unique mouse movement characteristics.

## Features

- Real-time mouse movement tracking with 60fps optimization
- Advanced movement pattern analysis
- Neural network-based user identification with confidence scoring
- Sliding window prediction averaging
- Stability and confidence metrics
- Real-time identification with visual feedback
- Responsive visualization of predictions

## How It Works

The system works in three main steps:

1. **Data Collection**
   - Records mouse movements at 60fps
   - Captures comprehensive movement metrics:
     - Speed and acceleration
     - Direction changes
     - Path curvature
     - Position coordinates
   - Creates feature vectors from movement windows
   - Stores data separately for each registered user

2. **Model Training**
   - Processes collected movement data into training samples
   - Creates a neural network using TensorFlow.js
   - Trains the model using collected user data
   - Uses regularization, batch normalization, and dropout
   - Provides real-time training progress feedback
   - Monitors validation accuracy

3. **User Identification**
   - Captures live mouse movements at 60fps
   - Extracts 8 distinct movement features in real-time
   - Uses sliding window averaging for stable predictions
   - Applies confidence thresholds (65%)
   - Monitors prediction stability
   - Updates predictions continuously with visual feedback

## Technical Details

### Neural Network Architecture
- Input layer: 8 features
  - Average and maximum speed
  - Average and maximum acceleration
  - Direction change frequency
  - Path curvature
  - Normalized X and Y coordinates
- Hidden layers:
  - Dense layer (64 units, ReLU activation, L2 regularization)
  - Batch normalization
  - Dropout layer (30% dropout rate)
  - Dense layer (32 units, ReLU activation, L2 regularization)
  - Batch normalization
  - Dropout layer (30% dropout rate)
- Output layer: Softmax activation (number of units = number of users)

### Movement Features
- **Speed Metrics**
  - Average movement speed
  - Maximum speed
  - Average acceleration
  - Maximum acceleration
- **Pattern Analysis**
  - Direction change frequency
  - Path curvature ratio
  - Normalized screen position
  - Movement consistency

### Training Parameters
- Epochs: 100
- Batch size: 32
- Validation split: 20%
- Optimizer: Adam (learning rate: 0.001)
- Loss function: Categorical Cross-entropy
- L2 Regularization: 0.01

### Real-time Processing
- Frame rate: 60fps
- Prediction window: 10 samples
- Confidence threshold: 65%
- Stability monitoring
- Memory-optimized tensor operations

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
   - Monitor training progress and validation accuracy
   - Training completes in approximately 100 epochs
   - Watch for convergence in training/validation metrics

4. **Identifying Users**
   - Click "Start Identification" to begin
   - Move the mouse naturally
   - View real-time predictions with confidence scores
   - Monitor stability and confidence metrics
   - System shows "Uncertain" when confidence is low
   - Click "Stop Identification" to end the session

## Requirements

- Modern web browser with JavaScript enabled
- WebGL 2.0 support
- TensorFlow.js (loaded automatically from CDN)
- 60fps capable display (recommended)

## Technical Requirements

- Browser with WebGL 2.0 support
- Sufficient GPU memory for model training
- Stable internet connection (for loading TensorFlow.js)
- Display with 60Hz refresh rate (recommended)

## Limitations

- Requires sufficient training data for accurate identification
- Performance depends on GPU capabilities
- Requires at least 2 users for training
- Best results with consistent mouse movement patterns
- May show "Uncertain" when confidence is low
- Requires stable 60fps for optimal performance

## Privacy Note

This system runs entirely in the browser. No data is sent to any server, and all processing happens locally on your device. Mouse movement data is stored only in temporary browser memory.

## License

MIT License - Feel free to use, modify, and distribute this code for any purpose. 