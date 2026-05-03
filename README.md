# homebrew-cogo
                                                                                                                                                                                          
[Homebrew](https://brew.sh) tap for [Cogo](https://github.com/go-steer/cogo) — a terminal-native agentic CLI for Go developers, built on the Google ADK and Gemini 3.x.                   
 
This repository hosts the Homebrew formula and is updated automatically by Cogo's release workflow on every published version. You shouldn't need to interact with it directly — install  
Cogo via the tap and Homebrew handles the rest.           
                                                                                                                                                                                          
## Install                                                

```bash
brew install go-steer/cogo/cogo
```                                                                                                                                                                                       
 
The first run implicitly taps `go-steer/cogo` (this repository); subsequent installs and upgrades use the cached tap.                                                                     
                                                          
If you'd rather tap explicitly first:                                                                                                                                                     
                                                          
```bash                                                                                                                                                                                   
brew tap go-steer/cogo                                    
brew install cogo
```                                                                                                                                                                                       
 
## Verify                                                                                                                                                                                 
                                                          
```bash
cogo --version
# cogo v0.1.0 (commit abcdef12, built 2026-05-03T...)
```                                                                                                                                                                                       
 
## Upgrade                                                                                                                                                                                
                                                          
```bash
brew update
brew upgrade cogo                                                                                                                                                                         
```                                                                                                                                                                                       
                                                                                                                                                                                          
`brew update` refreshes the tap; `brew upgrade cogo` pulls in the latest formula.                                                                                                         
                                                          
## Uninstall                                                                                                                                                                              
                                                          
```bash                                                                                                                                                                                   
brew uninstall cogo            # remove the binary
brew untap go-steer/cogo       # remove the tap (optional)                                                                                                                                
```                                                                                                                                                                                       
                                                                                                                                                                                          
## Supported platforms                                                                                                                                                                    
                                                          
The formula installs the appropriate pre-built binary from [Cogo's GitHub Releases](https://github.com/go-steer/cogo/releases) for your platform:                                         
                                                          
| Platform              | Asset bundled in the formula                   |                                                                                                                
|-----------------------|------------------------------------------------|
| macOS Intel           | `cogo_<version>_darwin_amd64.tar.gz`           |                                                                                                                
| macOS Apple Silicon   | `cogo_<version>_darwin_arm64.tar.gz`           |                                                                                                                
| Linux amd64           | `cogo_<version>_linux_amd64.tar.gz`            |                                                                                                                
| Linux arm64           | `cogo_<version>_linux_arm64.tar.gz`            |                                                                                                                
                                                                                                                                                                                          
Each release also publishes a `checksums.txt` (SHA256); the formula pins the matching SHA256 per platform.                                                                                
                                                                                                                                                                                          
## How the formula gets updated                                                                                                                                                           
                                                          
Every time Cogo cuts a release (`git tag v<x.y.z>` on `main` triggers [`.github/workflows/release.yml`](https://github.com/go-steer/cogo/actions/workflows/release.yml)),                 
[goreleaser](https://goreleaser.com) builds the binaries, publishes the GitHub release, and pushes a fresh `Formula/cogo.rb` to this repo. There is no manual editing — please don't open
PRs against the formula directly.                                                                                                                                                         
                                                          
If a release seems to be missing here, check the [release workflow](https://github.com/go-steer/cogo/actions/workflows/release.yml) on the main repo for failures.                        

## Issues                                                                                                                                                                                 
                                                          
Bugs in Cogo itself — and any problems with installation via this tap — should be filed on the main project:                                                                              

→ [github.com/go-steer/cogo/issues](https://github.com/go-steer/cogo/issues)                                                                                                              
                                                          
## Other distribution channels

If Homebrew isn't your thing, Cogo is also published as:

- A multi-arch container image: `docker pull ghcr.io/go-steer/cogo:latest`
- Pre-built tarballs on every [GitHub release](https://github.com/go-steer/cogo/releases/latest)
- `go install github.com/go-steer/cogo/cmd/cogo@latest`

See the [install docs](https://go-steer.github.io/cogo/docs/getting-started/install/) for the full matrix.                                                                                

## License                                                                                                                                                                                
                                                          
The formula in this repository is released under the [Apache License 2.0](LICENSE), matching Cogo itself. 
