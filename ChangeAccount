import shutil
import os
import subprocess
import time

BASE_DIR = os.path.join(os.environ["LOCALAPPDATA"],r"Riot Games\Riot Client\Data")
TARGET_FILE = "RiotGamesPrivateSettings.yaml"

def copy_yaml(profile_name):
    source_folder = os.path.join(BASE_DIR, profile_name)
    source_path = os.path.join(source_folder, TARGET_FILE)
    dest_path = os.path.join(BASE_DIR, TARGET_FILE)

    print(f"\nLooking for: {source_path}")
    if not os.path.isfile(source_path):
        print(f"❌ File not found: {source_path}")
        return False

    try:
        shutil.copy2(source_path, dest_path)
        print(f"✅ Copied {TARGET_FILE} from {profile_name} to parent folder.")
        return True
    except Exception as e:
        print(f"❌ Error copying file: {e}")
        return False

def close_riot_client():
    print("\n🛑 Closing Riot Client...")
    try:
        subprocess.run(["taskkill", "/f", "/im", "RiotClientServices.exe"], check=True, stdout=subprocess.DEVNULL)
        print("✅ Riot Client closed.")
    except subprocess.CalledProcessError:
        print("⚠️ Riot Client was not running.")

def start_riot_client():
    print("\n🚀 Starting Riot Client...")
    riot_path = r"C:\Riot Games\Riot Client\RiotClientServices.exe"
    if os.path.exists(riot_path):
        subprocess.Popen(f'start "" "{riot_path}"', shell=True)
        print("✅ Riot Client started.")
    else:
        print("❌ Riot Client not found at:", riot_path)

def main():
    folder = input("Enter folder name: ").strip()

    if copy_yaml(folder):
        close_riot_client()
        time.sleep(3)
        start_riot_client()
    else:
        print("❌ Failed to copy file. Riot not restarted.")
        
    print("\nExiting in 3 seconds...")
    time.sleep(3)


if __name__ == "__main__":
    main()
