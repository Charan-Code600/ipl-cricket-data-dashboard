




import pandas as pd
import matplotlib.pyplot as plt

FILE = "ipl_matches.csv"
RAW_COLUMNS = ["Season", "Team1", "Team2", "Winner", "Venue", "PlayerOfMatch"]

print("""

************************************************
╔══════════════════════════════════════════════╗
║         IPL/CRICKET DATA DASHBOARD           ║
╚══════════════════════════════════════════════╝
************************************************

    View All Matches             enter ---> 1
    Team-wise Wins               enter ---> 2
    Head-to-Head Record          enter ---> 3
    Top Player of the Match      enter ---> 4
    Venue-wise Match Count       enter ---> 5
    Season-wise Champion         enter ---> 6
    Visualize Data (Chart)       enter ---> 7
    Exit                         enter ---> 8

************************************************
""")

def main():
    df = load_data()

    while True:
        print()
        print("*"*70)
        print()
        choice = input("Enter your choice: ").strip()

        try:
            if choice == "1":
                view_all_matches(df)
            elif choice == "2":
                team_wise_wins(df)
            elif choice == "3":
                head_to_head(df)
            elif choice == "4":
                top_player(df)
            elif choice == "5":
                venue_wise_count(df)
            elif choice == "6":
                season_wise_champion(df)
            elif choice == "7":
                visualize_data(df)
            elif choice == "8":
                print("Exiting program...")
                break
            else:
                print("Invalid choice! Please enter a number between 1-8.")
        except Exception as e:
            print(f"\nSomething went wrong: {e}")
            print("Please try again.")


def load_data():
    try:
        return pd.read_csv(FILE)
    except (FileNotFoundError, pd.errors.EmptyDataError):
        print(f"\n'{FILE}' not found or empty. Please add match data to this file first.")
        data = pd.DataFrame(columns=RAW_COLUMNS)
        data.to_csv(FILE, index=False)
        return data


def view_all_matches(df):
    if df.empty:
        print("\nNo match data found. Please add data to the CSV file.")
        return
    print(f"\nAvailable columns: {list(df.columns)}\n")
    print(df.to_string(index=False))


def team_wise_wins(df):
    if df.empty:
        print("\nNo match data found.")
        return
    wins = df["Winner"].value_counts()
    print("\n--- Team-wise Wins ---")
    print(wins.to_string())


def head_to_head(df):
    if df.empty:
        print("\nNo match data found.")
        return

    team_a = input("Enter Team 1: ").strip().upper()
    team_b = input("Enter Team 2: ").strip().upper()

    matches = df[
        ((df["Team1"].str.upper() == team_a) & (df["Team2"].str.upper() == team_b)) |
        ((df["Team1"].str.upper() == team_b) & (df["Team2"].str.upper() == team_a))
    ]

    if matches.empty:
        print(f"\nNo matches found between {team_a} and {team_b}.")
        return

    total = len(matches)
    a_wins = len(matches[matches["Winner"].str.upper() == team_a])
    b_wins = len(matches[matches["Winner"].str.upper() == team_b])

    print(f"\nHead-to-Head: {team_a} vs {team_b}")
    print(f"Total Matches: {total}")
    print(f"{team_a} Wins: {a_wins}")
    print(f"{team_b} Wins: {b_wins}")


def top_player(df):
    if df.empty:
        print("\nNo match data found.")
        return
    top = df["PlayerOfMatch"].value_counts().head(5)
    print("\n--- Top 5 Players of the Match ---")
    print(top.to_string())


def venue_wise_count(df):
    if df.empty:
        print("\nNo match data found.")
        return
    venues = df["Venue"].value_counts()
    print("\n--- Venue-wise Match Count ---")
    print(venues.to_string())


def season_wise_champion(df):
    if df.empty:
        print("\nNo match data found.")
        return

    print("\n--- Season-wise Champion (last match winner per season) ---")
    for season in sorted(df["Season"].unique()):
        season_df = df[df["Season"] == season]
        champion = season_df["Winner"].iloc[-1]
        print(f"{season}: {champion}")


def visualize_data(df):
    if df.empty:
        print("\nNo match data found. Nothing to visualize.")
        return

    wins = df["Winner"].value_counts()
    plt.bar(wins.index, wins.values, color="skyblue")
    plt.xlabel("Team")
    plt.ylabel("Number of Wins")
    plt.title("IPL Team-wise Wins")
    plt.xticks(rotation=45, ha="right")
    plt.tight_layout()
    plt.show()


if __name__ == "__main__":
    main()








