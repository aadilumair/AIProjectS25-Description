# MLP-based AI Driver for TORCS

![TORCS Car](https://upload.wikimedia.org/wikipedia/commons/3/36/Torcs-title.png)

Built by [mahsna0838](https://github.com/mahsna0838), [aadilumair](https://github.com/aadilumair), and [HamzaSabirWorkspace](https://github.com/HamzaSabirWorkspace) for AI final project at FAST session Spring 2025.

## About TORCS and SCR

[TORCS (The Open Racing Car Simulator)](https://sourceforge.net/projects/torcs/) is an open-source 3D racing simulator that provides a realistic environment for developing and testing autonomous racing algorithms. The [SCR (Simple Car Racing) Championship](https://sourceforge.net/projects/cig/files/SCR%20Championship/) is a competition framework built on top of TORCS that enables AI agents to compete in racing scenarios.

## Project Overview

This project implements an AI driver for TORCS using a Multi-Layer Perceptron (MLP) neural network. The development process followed these steps:

1. **Data Collection**: We developed a custom TORCS client that collects sensor data while driving. The client supports both human control (keyboard/gamepad) and AI control modes. Sensor data is logged to CSV files, capturing:
   - Car state (position, speed, angle, etc.)
   - Track sensors (19 distance sensors)
   - Opponent sensors (36 distance sensors)
   - Control inputs (acceleration, braking, steering, gear)

2. **Model Training**: Using scikit-learn's MLPRegressor, we trained several neural networks. Feature weights were applied to prioritize important inputs.

3. **Evaluation**: The models were automatically evaluated using:
   - Regression metrics (MAE, RMSE, R²) for continuous outputs
   - Classification metrics (accuracy, F1) for gear selection
   - Safety checks for control output ranges

4. **Real-world Testing**: The trained model was integrated back into the TORCS client for real-time racing performance.

## Repository Structure

- **[AIProjectS25-TORCS-Client](https://github.com/aadilumair/AIProjectS25-TORCS-Client)**: Custom TORCS client implementation with data collection and AI control capabilities
- **[AIProjectS25-Dataset](https://github.com/aadilumair/AIProjectS25-Dataset)**: Collection of sensor logs used for training and evaluation
- **[AIProjectS25-Model-Trainer](https://github.com/aadilumair/AIProjectS25-Model-Trainer)**: MLP model training and evaluation code
- **[AIProjectS25-Models](https://github.com/aadilumair/AIProjectS25-Models)**: Trained model files and evaluation reports

## Contributing

1. Fork the relevant repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
