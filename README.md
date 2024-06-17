# ai-smartwatch-disease-detection
import numpy as np

def process_heart_rate_data(heart_rate_data):
    """Normalize heart rate data."""
    heart_rate_array = np.array(heart_rate_data)
    normalized_heart_rate = (heart_rate_array - heart_rate_array.mean()) / heart_rate_array.std()
    return normalized_heart_rate

def process_accelerometer_data(accelerometer_data):
    """Convert accelerometer data into a feature vector."""
    feature_vector = []
    for data in accelerometer_data:
        feature_vector.append(data["x"])
        feature_vector.append(data["y"])
        feature_vector.append(data["z"])
    return np.array(feature_vector)

if __name__ == "__main__":
    heart_rate_data = [70, 75, 80, 65, 90]
    accelerometer_data = [
        {"x": 0.1, "y": 0.2, "z": -0.1},
        {"x": -0.3, "y": 0.4, "z": 0.0},
        {"x": 0.5, "y": -0.2, "z": 0.3}
    ]

    normalized_heart_rate = process_heart_rate_data(heart_rate_data)
    feature_vector = process_accelerometer_data(accelerometer_data)

    print(f"Normalized Heart Rate: {normalized_heart_rate}")
    print(f"Feature Vector: {feature_vector}")
