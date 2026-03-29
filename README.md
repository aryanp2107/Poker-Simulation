# Poker Simulation
 
A command-line poker hand simulator that uses probability to evaluate and compare hands. Built with Python and [Click](https://click.palletsprojects.com/).
 
## Features
 
- **Deal hands** — randomly deal one or more 5-card poker hands from a standard 52-card deck
- **Hand evaluation** — automatically classifies hands (Royal Flush → High Card) and assigns rank values
- **Interactive mode** — play multiple rounds against the computer with a betting system, expected value tracking, and round-by-round statistics
- **Probability reference** — view the probability and odds of every poker hand
- **Color-coded output** — red/black card suits and green/red/yellow result indicators in the terminal
 
## Hand Rankings
 
| Rank | Hand | Probability |
|------|------|-------------|
| 10 | Royal Flush | 0.000154% |
| 9 | Straight Flush | 0.00139% |
| 8 | Four of a Kind | 0.024% |
| 7 | Full House | 0.14% |
| 6 | Flush | 0.196% |
| 5 | Straight | 0.39% |
| 4 | Three of a Kind | 2.11% |
| 3 | Two Pair | 4.75% |
| 2 | One Pair | 42.2% |
| 1 | High Card | 50.1% |
 
## Setup
 
### Prerequisites
 
- Python 3.12+
 
### Installation
 
```bash
# Clone the repository
git clone https://github.com/aryanp2107/Poker-Simulation.git
cd Poker-Simulation
 
# Create and activate a virtual environment
python3 -m venv myenv
source myenv/bin/activate        # macOS/Linux
myenv\Scripts\activate           # Windows
 
# Install dependencies
pip install -r requirements.txt
```
 
### Dev Container (GitHub Codespaces / VS Code)
 
This project includes a `.devcontainer` configuration. To use it:
 
1. Open the repo in VS Code or GitHub Codespaces
2. When prompted, click **Reopen in Container**
3. The environment will set up automatically
 
## Usage
 
All commands are run through `poker.py`:
 
```bash
python poker.py [COMMAND] [OPTIONS]
```
 
### `deal` — Deal poker hands
 
```bash
python poker.py deal              # Deal a single hand
python poker.py deal --hands 5    # Deal 5 hands at once
```
 
### `info` — View hand rankings and probabilities
 
```bash
python poker.py info                  # Show all hand ranks with examples
python poker.py info --probability    # Include probability and odds for each hand
```
 
### `play` — Quick game against the computer
 
```bash
python poker.py play --name "Aryan" --bet 50 --hand 1
```
 
| Option | Default | Description |
|--------|---------|-------------|
| `--name` | Player | Your display name |
| `--hand` | 1 | Which hand to play (1 or 2) |
| `--bet` | 1 | Amount to wager |
 
### `interactive` — Multi-round session with betting
 
```bash
python poker.py interactive --name "Aryan" --rounds 10 --money 500
```
 
| Option | Default | Description |
|--------|---------|-------------|
| `--name` | Player | Your display name |
| `--rounds` | 1 | Number of rounds to play |
| `--money` | 100 | Starting bankroll |
 
Each round shows your hand, its probability, and prompts for a bet. After all rounds, a full summary is printed including wins, losses, ties, remaining money, expected value per round, and cumulative expected value vs actual earnings.
 
