just in one line in powershell:

# Create directories (only if they don't exist)

$null = New-Item -ItemType Directory -Force -Path src, src\components, src\components\common, src\components\common\Skeleton, src\components\common\providers, src\components\editor, src\components\pricing, src\components\profile, src\components\profile\ProfileSections, src\components\snippets, src\components\theme, src\constants, src\hooks, src\pages, src\store

# Create files (only if they don't exist)

$files = @(
"src\App.js",
"src\index.js",
"src\components\common\CodeBlock.jsx",
"src\components\common\CopyButton.jsx",
"src\components\common\Footer.jsx",
"src\components\common\LoginButton.jsx",
"src\components\common\NavigationHeader.jsx",
"src\components\common\StarButton.jsx",
"src\components\common\providers\ConvexClientProvider.jsx",
"src\components\common\Skeleton\EditorPanelSkeleton.jsx",
"src\components\common\Skeleton\ProfileHeaderSkeleton.jsx",
"src\components\common\Skeleton\RunningCodeSkeleton.jsx",
"src\components\common\Skeleton\SnippetLoadingSkeleton.jsx",
"src\components\editor\EditorPanel.jsx",
"src\components\editor\Header.jsx",
"src\components\editor\HeaderProfileBtn.jsx",
"src\components\editor\LanguageSelector.jsx",
"src\components\editor\OutputPanel.jsx",
"src\components\editor\RunButton.jsx",
"src\components\editor\ShareSnippetDialog.jsx",
"src\components\pricing\FeatureCategory.jsx",
"src\components\pricing\FeatureItem.jsx",
"src\components\pricing\ProPlanView.jsx",
"src\components\pricing\UpgradeButton.jsx",
"src\components\profile\ProfileHeader.jsx",
"src\components\profile\ProfileSections\CodeBlock.jsx",
"src\components\snippets\SnippetCard.jsx",
"src\components\snippets\Comments.jsx",
"src\components\snippets\CommentContents.jsx",
"src\components\snippets\CommentForm.jsx",
"src\components\theme\ThemeSelector.jsx",
"src\constants\editor.js",
"src\constants\pricing.js",
"src\constants\snippets.js",
"src\hooks\useMounted.js",
"src\pages\EditorPage.jsx",
"src\pages\PricingPage.jsx",
"src\pages\ProfilePage.jsx",
"src\pages\SnippetsPage.jsx",
"src\store\useCodeEditorStore.js"
)

foreach ($file in $files) {
if (!(Test-Path $file)) {
$null = New-Item -ItemType File -Path $file
}
}

Write-Host "Directory structure and files created successfully!" -ForegroundColor Green
