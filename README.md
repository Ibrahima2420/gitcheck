# This is the read me file
modified from github

# hook :
path = .git/hooks/pre-commit
#!/bin/bash
for file in $(git diff --cached --name-only | grep '\.md$'); do
    if ! grep -q "^# ." "$file"; then
        echo "ERROR : Le fichier $file n'a pas de titre Markdown"
        exit 1
    fi
done

