# GE_dcm_to_nii

A converter for dicom to nifti.

Added dockerfile generated manually (Dockerfile) and with [neurodocker](https://github.com/kaczmarj/neurodocker/tree/master/examples#neurodocker-examples) (NeuroDockerfile)

[Video about creating the Dockerfile](https://www.youtube.com/watch?v=fIwK3sP1sC0)

## Neurodocker Command

```bash
docker run --rm kaczmarj/neurodocker:0.5.0 generate docker --base ubuntu:xenial-20190122 --pkg-manager apt --install libgdcm-tools --fsl version=5.0.11 --freesurfer version=6.0.0-min install_path=/opt/freesurfer --afni version=latest --run "cd /opt/freesurfer && echo 'cHJpbnRmICJrcnp5c3p0b2YuZ29yZ29sZXdza2lAZ21haWwuY29tXG41MTcyXG4gKkN2dW12RVYzelRmZ1xuRlM1Si8yYzFhZ2c0RVxuIiA+IGxpY2Vuc2UudHh0Cg==' | base64 -d | sh" --copy "GE_dcm_to_nii.sh" "/opt/" --run "chmod +x /opt/GE_dcm_to_nii.sh" --entrypoint "/opt/GE_dcm_to_nii.sh" > NeuroDockerfile
```
