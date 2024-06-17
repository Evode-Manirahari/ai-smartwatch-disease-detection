# ai-smartwatch-disease-detection

import random
import time

def collect_heart_rate():
    """Simulate collecting heart rate data from the smartwatch."""
    return random.randint(60, 100)

def collect_accelerometer_data():
    """Simulate collecting accelerometer data from the smartwatch."""
    return {
        "x": random.uniform(-1, 1),
        "y": random.uniform(-1, 1),
        "z": random.uniform(-1, 1)
    }

def main():
    while True:
        heart_rate = collect_heart_rate()
        accelerometer_data = collect_accelerometer_data()
        print(f"Heart Rate: {heart_rate} bpm")
        print(f"Accelerometer Data: {accelerometer_data}")
        time.sleep(1)

if __name__ == "__main__":
    main()
