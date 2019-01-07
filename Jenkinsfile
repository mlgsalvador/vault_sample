node {
  def secrets = [
      [$class: 'VaultSecret', path: 'secret/hello', secretValues: [
          [$class: 'VaultSecretValue', envVar: 'first_secret', vaultKey: 'accenture']]],
  ]
  def configuration = [$class: 'VaultConfiguration',
                       vaultUrl: 'http://100.26.111.13:8200',
                       vaultCredentialId: 'VAULT_ROOT_TOKEN']
                       
  wrap([$class: 'VaultBuildWrapper', configuration: configuration, vaultSecrets: secrets]) {
      sh 'echo $first_secret > test_secret'
  }
}
