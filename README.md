# 🎨 Contributions Painter

Create custom text and patterns on your GitHub contribution graph! Draw designs, spell out words, or make pixel art using your commit history.

## 🌟 Features

- 🖌️ **Visual Editor** - Draw patterns with click and drag
- ⌨️ **Text to Pattern** - Type text and instantly convert to contribution pattern
- 🎨 **4 Intensity Levels** - Create different shades of green (1=light, 4=dark)
- 📥 **Multiple Export Options** - GitHub Actions (YAML) or Python script
- 🖱️ **Easy Controls** - Left-click to draw, right-click to erase

## 🚀 Live Demo

Try it out: **[https://drbaph.is.a.dev/contributions-painter](https://drbaph.is.a.dev/contributions-painter)**

## 📖 How It Works

This tool creates backdated commits on specific dates to form patterns on your GitHub contribution graph. The graph shows 7 rows (days of the week) × 53 columns (weeks), giving you a 7×53 pixel canvas.

### Intensity Levels
- **Level 1** = 1 commit per day (lightest green)
- **Level 2** = 2 commits per day
- **Level 3** = 3 commits per day
- **Level 4** = 4 commits per day (darkest green)

## 🛠️ Usage

### Method 1: GitHub Actions (Recommended)

1. **Design Your Pattern**
   - Visit the [live demo](https://drbaph.is.a.dev/contributions-painter)
   - Type text or draw your pattern
   - Select intensity level (1-4)
   - Click **"GitHub Action (YAML)"** to download

2. **Setup Repository**
   ```bash
   # Create a new repository or use existing one
   mkdir my-contribution-pattern
   cd my-contribution-pattern
   git init
   ```

3. **Add Workflow File**
   ```bash
   # Create the workflows directory
   mkdir -p .github/workflows
   
   # Move your downloaded file there
   mv ~/Downloads/contribution-pattern.yml .github/workflows/
   ```

4. **Commit and Push**
   ```bash
   git add .github/workflows/contribution-pattern.yml
   git commit -m "Add contribution pattern workflow"
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

5. **Run the Workflow**
   - Go to your repository on GitHub
   - Click the **Actions** tab
   - Select **"Draw Contribution Pattern"**
   - Click **"Run workflow"** button
   - Wait 2-5 minutes for completion

6. **Check Your Profile**
   - Visit your GitHub profile
   - Your pattern should appear on the contribution graph!
   - Note: It may take a few minutes to update

#### Troubleshooting GitHub Actions

If the workflow fails with a permissions error:

1. Go to your repository **Settings**
2. Click **Actions** → **General**
3. Scroll down to **Workflow permissions**
4. Select **"Read and write permissions"**
5. Check **"Allow GitHub Actions to create and approve pull requests"** (optional)
6. Click **Save**
7. Re-run the workflow

### Method 2: Python Script (Local)

1. **Design Your Pattern**
   - Visit the [live demo](https://drbaph.is.a.dev/contributions-painter)
   - Create your pattern
   - Click **"Python Script"** to download

2. **Setup Repository**
   ```bash
   # Clone your repository
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
   cd YOUR_REPO
   ```

3. **Run the Script**
   ```bash
   # Make it executable (Linux/Mac)
   chmod +x create_pattern.py
   
   # Run it
   python3 create_pattern.py
   ```

4. **Push Changes**
   ```bash
   git push origin main
   ```

## ⚠️ Important Notes

- **Use a dedicated repository** - This modifies commit history
- **Public repositories only** - Private repo commits don't show on your profile by default
- **Be patient** - GitHub's contribution graph can take up to 24 hours to fully update
- **One-time use** - Once created, the pattern is permanent unless you delete the repo or force-push
- **Overwrites history** - Don't use this on repositories with important existing commits

## 🎯 Examples

### Simple Text
Type "HELLO" with intensity level 4 for maximum visibility.

### Your Name
Use intensity level 3 and type your GitHub username.

### Custom Patterns
Draw manually for pixel art, logos, or custom designs.

## 🔧 Advanced Usage

### Stopping the Pattern

**Option 1: Delete Repository** (Easiest)
- Simply delete the repository
- Commits will disappear from your graph within 24 hours

**Option 2: Remove Commits**
```bash
# Reset to before pattern commits
git reset --hard HEAD~[NUMBER_OF_COMMITS]

# Force push to overwrite
git push --force origin main
```

**Option 3: Disable Workflow**
- Go to Actions tab
- Click on the workflow
- Click "..." menu → "Disable workflow"

**Option 4: Make Repository Private**
- Go to Settings → Danger Zone
- Click "Change visibility" → "Make private"
- Private contributions won't show on public profile

### Scheduling Pattern Updates

The GitHub Action includes a cron schedule (commented out by default):
```yaml
schedule:
  - cron: '0 0 * * 0'  # Run weekly on Sunday
```

Uncomment this to automatically refresh your pattern weekly.


## 📝 License

This project is open source and available under the MIT License.

## ⭐ Support

If you find this tool useful, please consider giving it a star on GitHub!

## 🔗 Links

- **Live Demo**: [https://drbaph.is.a.dev/contributions-painter](https://drbaph.is.a.dev/contributions-painter)

---

**Made for the GitHub community** 🎨
