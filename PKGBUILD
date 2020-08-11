# Maintainer: Stas Rudakou <stas at garage22 dot net>

pkgname=go-jira-bin
conflicts=('go-jira')
pkgver=1.0.23
pkgrel=2
pkgdesc="Simple command line client for Atlassian's Jira service written in Go"
url="https://github.com/Netflix-Skunkworks/go-jira"
arch=('x86_64')
license=('APACHE')
source=("jira-$pkgver::https://github.com/Netflix-Skunkworks/go-jira/releases/download/v$pkgver/jira-linux-amd64")
sha256sums=('e2550f69ed5471bf4699554ff72b4bb41445266ae3a2c02a4594cd0557dd1f2a')

package() {
  install -Dm755 jira-$pkgver "$pkgdir/usr/bin/jira"
  install -dm755 "$pkgdir/usr/share/zsh/site-functions"
  install -dm755 "$pkgdir/usr/share/bash-completion/completions"
  "$pkgdir/usr/bin/jira" --completion-script-zsh \
    > "$pkgdir/usr/share/zsh/site-functions/_jira" || true
  "$pkgdir/usr/bin/jira" --completion-script-bash \
    > "$pkgdir/usr/share/bash-completion/completions/jira" || true
}
