github/workflows/github-actions-demo.yml# - name: Download artifact
  uses: actions/download-artifact@v4
  with:
    name: ${{ inputs.artifact_name }}

- name: Extract tarball
  env:
    ARTIFACT_NAME: ${{ inputs.artifact_name }}
  run: |
    tarball="$ARTIFACT_NAME.tar"
    tar --extract --file "$tarball"
    rm "$tarball"
Adshopper is an Android app that helps users earn money online by interacting with sponsored content. It features dual profiles (Adshopper &amp; Adloader), and includes auto APK builds with GitHub Actions.
