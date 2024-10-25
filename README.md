# Simple Git Demo

This is a simple project to demonstrate different Git strategies, such as:

- Feature Branches
- Git Flow
- GitHub Flow
- Trunk-Based Development

1. Feature Branches

# Starta ett nytt Git-repo
git init
git add .
git commit -m "Initial commit with project structure"

# Skapa en ny feature branch
git branch feature-update-header
git switch feature-update-header

# Gör en ändring i index.html, till exempel ändra rubriken
# Commit ändringen
git add index.html
git commit -m "Update header text in index.html"

# Byt tillbaka till main och slå ihop feature-branchen
git switch main
git merge feature-update-header
git branch -d feature-update-header

# Push till fjärrrepository (om uppkopplat)
git push origin main

2. Git Flow

# Initiera Git Flow (kräver att Git Flow är installerat)
git flow init

# Skapa en ny feature
git flow feature start update-styles

# Gör en ändring i style.css, exempelvis uppdatera bakgrundsfärgen
git add styles/style.css
git commit -m "Update background color in style.css"

# Avsluta featuren och slå ihop den med develop
git flow feature finish update-styles

# Skapa en release
git flow release start v1.0.0
git flow release finish v1.0.0

# Deploya genom att mergea till main och tagga versionen
git push origin main --tags

3. GitHub Flow

# Skapa en ny branch direkt från main
git checkout -b feature-add-footer

# Lägg till en footer i index.html
git add index.html
git commit -m "Add footer to index.html"

# Push till fjärrrepository och skapa en Pull Request
git push origin feature-add-footer

# När Pull Request är granskad och godkänd, slå ihop den med main via GitHub.
# Sedan, på din lokala maskin, hämta och uppdatera main.
git switch main
git pull origin main

4. Trunk-Based Development

# Gör en snabb fix direkt i main
# Uppdatera till exempel en text i README.md
git add README.md
git commit -m "Update README.md with more details"

# För en större förändring, skapa en kortlivad branch
git checkout -b quick-fix-header

# Uppdatera rubriken i index.html
git add index.html
git commit -m "Quick fix for header"

# Slå snabbt ihop med main
git checkout main
git merge quick-fix-header
git branch -d quick-fix-header

# Push ändringarna direkt
git push origin main
