import subprocess
import sys
import os

def create_virtualenv(env_name='venv'):
    if not os.path.exists(env_name):
        print(f"Creating virtual environment: {env_name}")
        subprocess.check_call([sys.executable, '-m', 'venv', env_name])
    else:
        print(f"Virtual environment '{env_name}' already exists.")

def install_dependencies(requirements_file='requirements.txt'):
    print(f"Installing dependencies from {requirements_file}...")
    subprocess.check_call([sys.executable, '-m', 'pip', 'install', '-r', requirements_file])

if __name__ == '__main__':
    create_virtualenv()
    install_dependencies()
