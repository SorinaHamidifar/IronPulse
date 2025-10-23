# ================================
# Project: PulseHub 
# Description:
# A living, breathing hub for bold experiments and high-impact solutions.
# Designed to deliver strength and adaptability in every project.
# ================================

# ---------- main.py ----------
"""
Main entry point for PulseHub.
"""

from core import engine, adapt


def run():
    print("🌍 Welcome to Pulse")
    print("⚡ Bold Experiments | 💥 High-Impact Solutions | 🔁 Adaptability\n")

    # Demo features
    data = [3, 9, 27, 81]
    print("🔥 Experiment Result (power growth):", engine.power_growth(data, factor=2))
    print("🧠 Adaptive Insight:", adapt.dynamic_adjustment(score=0.68))
    print("💪 System Pulse:", engine.system_pulse())


if __name__ == "__main__":
    run()


# ---------- core/engine.py ----------
"""
Core experimentation engine.
Handles logic for experimental computations and high-impact prototypes.
"""

import time
import math

def power_growth(values, factor=2):
    """Scale a list of values exponentially to simulate experimental growth."""
    return [v * (factor ** i) for i, v in enumerate(values)]

def system_pulse():
    """Simulate a 'heartbeat' signal for system health."""
    pulse = {"status": "active", "timestamp": time.time(), "load": round(math.sin(time.time()) * 50, 2)}
    return pulse


# ---------- core/adapt.py ----------
"""
Adaptability and smart-response utilities.
Helps the system evolve and tune itself dynamically.
"""

def dynamic_adjustment(score: float) -> str:
    """
    Analyze a score and return an adaptive system response.
    """
    if score >= 0.8:
        return "System Stable: High performance maintained ✅"
    elif score >= 0.5:
        return "System Balanced: Minor tuning recommended ⚙️"
    else:
        return "System Alert: Significant adaptation required 🚨"

def evolve_parameters(params: dict, learning_rate: float = 0.1) -> dict:
    """
    Simulate adaptive parameter tuning.
    """
    return {k: round(v * (1 + learning_rate), 3) for k, v in params.items()}


# ---------- tests/test_adapt.py ----------
"""
Unit tests for adapt.py
Run with: pytest
"""

from core import adapt

def test_dynamic_adjustment():
    assert "Stable" in adapt.dynamic_adjustment(0.9)
    assert "Balanced" in adapt.dynamic_adjustment(0.6)
    assert "Alert" in adapt.dynamic_adjustment(0.2)

def test_evolve_parameters():
    params = {"alpha": 1.0, "beta": 2.0}
    evolved = adapt.evolve_parameters(params, 0.1)
    assert evolved["alpha"] == 1.1
    assert evolved["beta"] == 2.2
