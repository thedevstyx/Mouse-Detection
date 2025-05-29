# Mouse Movement User Identification System

A web-based biometric authentication system that identifies users based on their unique mouse movement patterns using deep learning. The system runs entirely in the browser using TensorFlow.js with GPU acceleration.

## Overview

This system uses mouse movement patterns as a behavioral biometric to identify users. It captures features like:
- Mouse movement speed
- Movement patterns
- Average positions
- Speed variations

## Technical Architecture

### Neural Network Model
- 6-layer deep neural network
- Architecture: 64→48→32→24→16→output neurons
- Features:
  - Batch Normalization for training stability
  - Dropout layers (30-40%) for regularization
  - L2 regularization (0.02) to prevent overfitting
  - Adam optimizer with 0.0001 learning rate
  - Temperature scaling for confidence calibration

### GPU Acceleration
- Uses WebGL backend for GPU acceleration
- WebGL 2.0 with fallback to 1.0
- Optimized memory management
- Batch processing for efficient training
- Real-time prediction capabilities

### Data Collection
- Collects mouse movement data in real-time
- Features extracted:
  - Average speed
  - Maximum speed
  - Average X/Y positions
- Uses a sliding window of 20 points
- Rolling prediction window of 220 samples

## Features

1. **User Registration**
   - Record mouse movement patterns
   - Multiple users support
   - Real-time data collection

2. **Model Training**
   - GPU-accelerated training
   - Progress visualization
   - Validation split: 20%
   - 500 epochs with early stopping

3. **Real-time Identification**
   - Continuous user identification
   - Confidence scoring
   - Rolling window predictions
   - Dual confidence display:
     - Average confidence over time
     - Current prediction confidence

4. **Visual Feedback**
   - Active identification status
   - Training progress
   - GPU utilization monitoring
   - Memory usage tracking
   - Confidence visualization bars

## How to Use

1. **Registration**
   - Enter username
   - Click "Start Recording"
   - Move mouse naturally for 30-60 seconds
   - Click "Stop Recording"
   - Repeat for each user

2. **Training**
   - Register at least 2 users
   - Click "Train Neural Network Model"
   - Wait for training completion
   - Monitor progress in status display

3. **Identification**
   - Click "Start Identification"
   - Move mouse naturally
   - Watch real-time predictions
   - Monitor confidence levels
   - Click "Stop Identification" when done

## Performance Metrics

- Training time: Varies by GPU capability
- Prediction latency: Real-time
- Memory usage: Monitored and displayed
- GPU utilization: Optimized for WebGL

## Technical Requirements

- Modern web browser (Chrome recommended)
- WebGL support
- GPU with hardware acceleration
- Sufficient RAM (4GB minimum)

## Implementation Details

### Data Processing
- Real-time feature extraction
- Sliding window approach
- Normalized inputs
- Temperature-scaled predictions

### Model Architecture
```javascript
model = tf.sequential({
  layers: [
    tf.layers.dense({inputShape: [4], units: 64, activation: 'relu'}),
    tf.layers.batchNormalization(),
    tf.layers.dropout({rate: 0.3}),
    // ... additional layers
    tf.layers.dense({units: numUsers, activation: 'softmax'})
  ]
});
```

### Optimization Features
- Batch processing
- GPU memory management
- Tensor cleanup
- Performance monitoring

## Security Considerations

- Data stays in browser (no server communication)
- Model runs locally
- No persistent storage
- Privacy-preserving design

## Limitations

- Requires GPU support
- Browser-dependent performance
- Requires sufficient training data
- May need retraining for best results

## Future Improvements

- Model persistence
- Additional biometric features
- Enhanced preprocessing
- Advanced feature extraction
- Cross-session reliability

## Troubleshooting

If experiencing high CPU usage:
1. Check browser GPU acceleration settings
2. Monitor console for WebGL status
3. Verify GPU initialization
4. Check memory usage statistics

## Credits

Built using:
- TensorFlow.js 4.15.0
- WebGL 2.0/1.0
- Modern JavaScript
- HTML5/CSS3 