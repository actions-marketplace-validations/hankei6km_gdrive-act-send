# Google Drive tools Action - send

This action sends a file to Google Drive.



## Inputs

| parameter | description | required | default |
| - | - | - | - |
| parent_id | The ID of the parent folders in remote | `true` |  |
| dest_file_name | The name of the file in remote | `true` |  |
| src_file_name | The name(path) of the file in local filesystem | `true` |  |
| dest-mime-type | The MIME type of the file. | `false` |  |
| src-mime-type | Media mime-type | `false` |  |


## Outputs

| parameter | description |
| - | - |
| file_id | The ID of the file that is sended into Google Drive |


## Runs

This action is an `node16` action.



## Example usage

```yaml
- id: 'auth'
  name: 'Authenticate to Google Cloud'
  uses: 'google-github-actions/auth@v0'
  with:
    workload_identity_provider: ${{ secrets.WORKLOAD_IDENTITY_PROVIDER }}
    service_account: ${{ secrets.SERVICE_ACCOUNT }}

- name: Send file
  id: send
  uses: hankei6km/gdrive-act-send@v0.2
  with:
    parent-id: ${{ secrets.PARENT_ID }}
    dest-file-name: ${{ secrets.DEST_FILE_NAME }}
    src-file-name: ${{ secrets.SRC_FILE_NAME }}
```

## Licenses

MIT License

Copyright (c) 2022 hankei6km
