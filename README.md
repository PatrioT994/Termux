# Termux
Termux Github user sign in
import os

def set_github_credentials():
    # Kullanıcı adını ve tokeni alın
    username = os.environ["GITHUB_USERNAME"]
    token = os.environ["GITHUB_TOKEN"]

    # Kullanıcı adını ve tokeni Termux'a tanıştırın
    os.system("git config --global user.name '{}'".format(username))
    os.system("git config --global credential.helper 'store --file ~/.git-credentials'")
    os.system("echo '{username}:{token}' >> ~/.git-credentials")

if __name__ == "__main__":
    set_github_credentials()