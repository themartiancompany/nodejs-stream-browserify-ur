# SPDX-License-Identifier: AGPL-3.0

#    ---------------------------------
#    Copyright © 2024, 2025, 2026
#                Pellegrino Prevete
#
#    All rights reserved
#    ---------------------------------
#
#    This program is free software:
#    you can redistribute it and/or
#    modify it under the terms of
#    the GNU Affero General Public
#    License as published by
#    the Free Software Foundation,
#    either version 3 of the License,
#    or (at your option)
#    any later version.
#
#    This program is distributed in
#    the hope that it will be useful,
#    but WITHOUT ANY WARRANTY;
#    without even the implied warranty
#    of MERCHANTABILITY or FITNESS
#    FOR A PARTICULAR PURPOSE.
#    See the
#    GNU Affero General Public License
#    for more details.
#
#    You should have received a copy
#    of the GNU Affero General
#    Public License
#    along with this program.
#    If not, see
#    <https://www.gnu.org/licenses/>.

# Maintainers:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>

_os="$(
  uname \
    -o)"
_evmfs_available="$(
  command \
    -v \
    "evmfs" || \
    true)"
if [[ ! -v "_evmfs" ]]; then
  if [[ "${_evmfs_available}" != "" ]]; then
    _evmfs="true"
  elif [[ "${_evmfs_available}" == "" ]]; then
    _evmfs="false"
  fi
fi
_node="nodejs"
if [[ "${_os}" == "Android" ]]; then
  _node="nodejs-lts"
fi
if [[ ! -v "_npm" ]]; then
  _npm="false"
fi
if [[ ! -v "_git" ]]; then
  _git="false"
fi
if [[ ! -v "_git_service" ]]; then
  _git_service="github"
fi
if [[ ! -v "_git_http" ]]; then
  _git_http="${_git_service}"
fi
_archive_format="tgz"
if [[ ! -v "${_archive_format}" ]]; then
  if [[ "${_npm}" == "false" ]]; then
    if [[ "${_git_http}" == "github" ]]; then
      _archive_format="zip"
    fi
  fi
fi
_pkg=stream-browserify
pkgbase="nodejs-${_pkg}"
pkgname=(
  "${pkgbase}"
)
_pkgdesc=(
  "The stream module from Node"
  "core for browsers."
)
pkgdesc="${_pkgdesc[*]}"
_commit="a3625cb4181c4bcdf09884e677d4320c641b8724"
_pkgver="3.0.0"
pkgver="${_pkgver}"
pkgrel=1
arch=(
  'any'
)
_http="https://${_git_http}.com"
if [[ ! -v "_ns" ]]; then
  _ns="browserify"
  _ns="themartiancompany"
fi
url="${_http}/${_ns}/${_pkg}"
license=(
  'AGPL3'
)
depends=(
  "${_node}"
)
provides=(
  "${_pkg}=${pkgver}"
)
makedepends=(
  "npm"
)
if [[ "${_npm}" == "true" ]]; then
  _tag="${pkgver}"
  _tag_name="pkgver"
elif [[ "${_npm}" == "false" ]]; then
  _tag="${_commit}"
  _tag_name="commit"
fi
_tarname="${_pkg}-${_tag}"
_npm_tarname="${_ns}-${_pkg}-${_tag}"
_tarfile="${_tarname}.${_archive_format}"
_npm_tarfile="${_npm_tarname}.${_archive_format}"
_sum="c34bc49cff7d579e7cd7d4137fbb0cb56fc262afa6055a979ff023cf6917669c"
_sig_sum="58173ca10e4aee209376c820797119cc7c749bbdb6d86be7905003455c43c25c"
_bundle_sum="nope"
_bundle_sig_sum="nope"
_npm_sum="376fa4c0ffd38961cf23c210f8a8dbcc46b00862c1d1bce1bbc66f7ea9a433cf"
_npm_sig_sum="105901f24f74f0d3720081269064cb8d01bbba14320e814cce6038cbd56adaa4"
# Truocolo
_evmfs_ns="0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b"
# Dvorak
_evmfs_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
_evmfs_network="100"
_evmfs_address="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
_evmfs_dir="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}"
_evmfs_uri="${_evmfs_dir}/${_sum}"
_evmfs_src="${_tarfile}::${_evmfs_uri}"
_bundle_uri="${_evmfs_dir}/${_bundle_sum}"
_bundle_src="${_tarfile}::${_bundle_uri}"
_evmfs_npm_uri="${_evmfs_dir}/${_npm_sum}"
_evmfs_npm_src="${_tarfile}::${_evmfs_npm_uri}"
_evmfs_sig_uri="${_evmfs_dir}/${_sig_sum}"
_evmfs_sig_src="${_tarfile}.sig::${_evmfs_sig_uri}"
_bundle_sig_uri="${_evmfs_dir}/${_bundle_sig_sum}"
_bundle_sig_src="${_tarfile}.sig::${_bundle_sig_uri}"
_npm_sig_uri="${_evmfs_dir}/${_npm_sig_sum}"
_npm_sig_src="${_tarfile}.sig::${_npm_sig_uri}"
_npm_http="http://registry.npmjs.org"
source=()
sha256sums=()
if [[ "${_evmfs}" == "true" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_evmfs_npm_uri}"
    _sum="${_evmfs_npm_sum}"
    _sig_src="${_evmfs_npm_uri}"
    _sig_sum="${_npm_sig_sum}"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_git}" == "true" ]]; then
      _uri="${_bundle_uri}"
      _sum="${_bundle_sum}"
      _sig_src="${_bundle_sig_src}"
      _sig_sum="${_bundle_sig_sum}"
    elif [[ "${_git}" == "false" ]]; then
      _uri="${_evmfs_uri}"
      _sig_src="${_evmfs_sig_src}"
    fi
  fi
  source+=(
    "${_sig_src}"
  )
  sha256sums+=(
    "${_sig_sum}"
  )
elif [[ "${_evmfs}" == "false" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_npm_http}/${_pkg}/-/${_tarfile}"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_tag_name}" == 'pkgver' ]]; then
      if [[ "${_git_http}" == "gitlab" ]]; then
        _uri="${url}/archive/refs/tags/${_tag}.${_archive_format}"
      fi
    elif [[ "${_tag_name}" == "commit" ]]; then
      if [[ "${_git_http}" == "github" ]]; then
        _uri="${url}/archive/${_commit}.${_archive_format}"
      elif [[ "${_git_http}" == "gitlab" ]]; then
        _uri="${url}/-/archive/${_commit}/${_tarname}.${_archive_format}"
      fi
    fi
  fi
fi
if [[ "${_npm}" == "true" ]]; then
  _tarfile="${_npm_tarfile}"
fi
_src="${_tarfile}::${_uri}"
source+=(
  "${_src}"
)
sha256sums+=(
  "${_sum}"
)
if [[ "${_npm}" == "true" ]]; then
  noextract=(
    "${_tarfile}"
  )
fi
validpgpkeys=(
  # Truocolo
  #   <truocolo@aol.com>
  '97E989E6CF1D2C7F7A41FF9F95684DBE23D6A3E9'
  'DD6732B02E6C88E9E27E2E0D5FC6652B9D9A6C01'
  #   <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
  'F690CBC17BD1F53557290AF51FC17D540D0ADEED'
  # Pellegrino Prevete (dvorak)
  #   <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
  '12D8E3D7888F741E89F86EE0FEC8567A644F1D16'
)

build() {
  local \
    _files=()
  _files+=(
    "AUTHORS.rst"
    "COPYING"
    "README.md"
    "eslint.config.mjs"
    "fs-worker"
    "fs-worker.webpack.config.cjs"
    "man"
    "opfs"
    "package.json"
  )
  if [[ "${_npm}" == "false" ]]; then
    cd \
      "${_tarname}"
    mkdir \
      -p \
      "build"
    cp \
      -r \
      "${_files[@]}" \
      "build"
    cd \
      "build"
    npm \
      install
    npm \
      pack
    mv \
      "${_ns}-${_pkg}-${_pkgver}.tgz" \
      "${srcdir}"
  fi
}

package_nodejs-opfs() {
  local \
    _npm_options=() \
    _find_opts=()
  _npm_options=(
    -g 
    # --user 
    #   root 
    --prefix 
      "${pkgdir}/usr"
  )
  find_opts+=(
    -type
      "d"
    -exec
      chmod
        755
        '{}'
        +
  )
  npm \
    install \
    "${_npm_options[@]}" \
    "${srcdir}/${_ns}-${_pkg}-${_pkgver}.tgz"
  rm \
    -fr \
      "${pkgdir}/usr/etc"
  # Fix npm derp
  find \
    "${pkgdir}/usr" \
    "${_find_opts[@]}"
}

# vim:set sw=2 sts=-1 et:
