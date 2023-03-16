vars = {
  # This is used during the transition phase of moving infra repos to git
  # submodules. To add new deps here check with the Chrome Source Team.
  "infra_superproject_checkout": True,
  #
  # Set to True if internal repos should be checked out.
  "checkout_internal": False,
}


deps = {
  "build": {
    "url": "{chromium_git}/chromium/tools/build.git",
  },

  "testing_support": {
    "url": "{chromium_git}/infra/testing/testing_support.git",
  },

  "infra": {
    "url": "https://chromium.googlesource.com/infra/infra.git@" +
    "97953bef7aa32859474638b6dcfc0f42b1780677",
  },

  "infra_internal": {
    "url": "https://chrome-internal.googlesource.com/infra/infra_internal.git",
    "condition": "checkout_internal",
  },

  "bcid": {
    "url": "https://chrome-internal.googlesource.com/external/gob/team/bcid-software-team/provenance.git@" +
    "853c183f8c591f5d1eb17695125f0b5eb2d57abd",
    "condition": "checkout_internal",
  },

  "build_internal": {
    "url": "https://chrome-internal.googlesource.com/chrome/tools/build.git",
    "condition": "checkout_internal",
  },

  "puppet": {
    "url": "https://chrome-internal.googlesource.com/infra/puppet.git",
    "condition": "checkout_internal",
  },

  "systems": {
    "url": "https://chrome-internal.googlesource.com/chrome-golo/chrome-golo.git",
    "condition": "checkout_internal",
  },

  # Not runtime dependencies, just included for ease of development.
  "data/config": {
    "url": "https://chrome-internal.googlesource.com/infradata/config.git",
    "condition": "checkout_internal",
  },

  "data/gae": {
    "url": "https://chrome-internal.googlesource.com/infradata/gae.git",
    "condition": "checkout_internal",
  },

  "data/k8s": {
    "url": "https://chrome-internal.googlesource.com/infradata/k8s.git",
    "condition": "checkout_internal",
  },

  "data/rbe": {
    "url": "https://chrome-internal.googlesource.com/infradata/rbe.git",
    "condition": "checkout_internal",
  },

  "release_scripts": {
    "url": "https://chrome-internal.googlesource.com/chrome/tools/release/scripts.git",
    "condition": "checkout_internal",
  },
}

hooks = [
  {
    "pattern": ".",
    "action": [
      "python3", "-u", "./infra/bootstrap/remove_orphaned_pycs.py",
      "infra_internal"
    ],
  },
]

recursedeps = ["infra", "build", "build_internal"]