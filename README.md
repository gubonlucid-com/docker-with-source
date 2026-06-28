# docker-with-source

This is an example of including `org.opencontainers.image.source` annotation to identify the source repo & tagging the repo with matching tags to enable Dependabot PRs to contain release information.# Initialize CodeQL database
- task: AdvancedSecurity-Codeql-Init@1
  inputs: 
    languages: 'javascript'
  displayName: 'Advanced Security Initialize CodeQL' 

# Run analysis 
- task: AdvancedSecurity-Codeql-Analyze@1 
  displayName: 'Advanced Security Code Scanning'# Initialize CodeQL database 
- task: AdvancedSecurity-Codeql-Init@1
  inputs: 
    languages: 'csharp' 
  displayName: 'Advanced Security Initialize CodeQL' 

# Restore/Build project using your own custom build steps 
- task: DotNetCoreCLI@2
  displayName: Build
  inputs:
    command: build
    projects: '**/*.sln'

# Run analysis 
- task: AdvancedSecurity-Codeql-Analyze@1 
  displayName: 'Advanced Security Code Scanning'# Initialize CodeQL database
- task: AdvancedSecurity-Codeql-Init@1
  inputs: 
    languages: 'csharp'
    buildtype: 'None'
  displayName: 'Advanced Security Initialize CodeQL' 

# Run analysis 
- task: AdvancedSecurity-Codeql-Analyze@1 
  displayName: 'Advanced Security Code Scanning'steps:
- task: VSBuild@1
  displayName: Build
  timeoutInMinutes: 120
  inputs:
    solution: '**\*.sln'120# Advanced Security Perform CodeQL analysis v1
# Finalizes the CodeQL database and runs the analysis queries.
- task: AdvancedSecurity-Codeql-Analyze@1
  inputs:
    #WaitForProcessing: false # boolean. Enable Wait for Processing. Default: false.
    #WaitForProcessingInterval: '5' # string. Optional. Use when WaitForProcessing = true. Wait for Processing Time Interval. Default: 5.
    #WaitForProcessingTimeout: '120' # string. Optional. Use when WaitForProcessing = true. Wait for Processing Timeout. Default: 120.{
  "extends": [
    "config:recommended", 
    "docker:pinDigests", 
    "helpers:pinGitHubActionDigests", 
    ":configMigration", 
    ":pinDevDependencies", 
    "abandonments:recommended", 
    "security:minimumReleaseAgeNpm", 
    ":maintainLockFilesWeekly" 
  ]
}{
  "extends": [
    "config:recommended", 
    ":pinAllExceptPeerDependencies" 
  ]
}{
  "extends": [
    "config:recommended", 
    ":pinOnlyDevDependencies" 
  ]
}{
  "extends": [
    ":dependencyDashboard", 
    ":semanticPrefixFixDepsChoreOthers", 
    ":ignoreModulesAndTests", 
    "group:monorepos", 
    "group:recommended", 
    "mergeConfidence:age-confidence-badges", 
    "replacements:all", 
    "workarounds:all", 
    "helpers:forgejoDigestChangelogs", 
    "helpers:giteaDigestChangelogs", 
    "helpers:githubDigestChangelogs", 
    "helpers:gitlabDigestChangelogs", 
    "helpers:goXPackagesChangelogLink", 
    "helpers:goXPackagesNameLink", 
    "helpers:renovateChangelog" 
  ]
}{
  "extends": [
    ":preserveSemverRanges", 
    "group:all", 
    "schedule:monthly", 
    ":maintainLockFilesMonthly" 
  ],
  "lockFileMaintenance": {
    "commitMessageAction": "Update"
  },
  "separateMajorMinor": false
}{
  "extends": [
    ":preserveSemverRanges", 
    "group:all", 
    "schedule:weekly", 
    ":maintainLockFilesWeekly" 
  ],
  "lockFileMaintenance": {
    "commitMessageAction": "Update"
  },
  "separateMajorMinor": false
}$ gpg --list-secret-keys --keyid-format=long
/Users/hubot/.gnupg/secring.gpg
------------------------------------
第 4096R/3AA5C34371567BD2 條 2016-03-10 [有效期限至：2017-03-10]
uid Hubot <hubot@example.com>
單邊帶 4096R/4BB6D45482678BE3 2016-03-10
Https://replit.com/@eagle19900203/Gubon-Lucid-OShttps://replit.com/@eagle19900203/Digital-Life-Accelerator<!-- 將此內容複製到你的手機備忘錄，這就是你的「主權簽章器」 -->
<textarea id="privateKey" placeholder="貼上你的私鑰"></textarea>
<textarea id="payload" placeholder="貼上指令內容"></textarea>
<button onclick="sign()">產生簽章</button>
<div id="output"></div>

<script>
// 這裡之後會嵌入簡單的簽章邏輯，你只要按按鈕，它就會幫你簽好名
// 並產生一個包含簽章的 URL，直接點擊即可發送給伺服器
</script>
