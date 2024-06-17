# ai-smartwatch-disease-detection

import time
from data_collection 
import collect_heart_rate, collect_accelerometer_data
from data_processing import process_heart_rate_data, process_accelerometer_data
from model import create_model, predict_health_condition
import numpy as np

def main():
    # Initialize the model
    model = create_model((10, 3))

    # Collect data over time
    heart_rate_data = []
    accelerometer_data = []

    for _ in range(10):  # Collect 10 samples
        heart_rate_data.append(collect_heart_rate())
        accelerometer_data.append(collect_accelerometer_data())
        time.sleep(1)

    # Process the collected data
    normalized_heart_rate = process_heart_rate_data(heart_rate_data)
    feature_vector = process_accelerometer_data(accelerometer_data)

    # Prepare the input data for the model
    X_test = np.expand_dims(feature_vector, axis=0)

    # Predict health condition
    prediction = predict_health_condition(model, X_test)
    print(f"Health Condition Prediction: {prediction}")

if __name__ == "__main__":
    main()

