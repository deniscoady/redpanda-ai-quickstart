# Pipelines Directory

This directory is meant to store all of your Redpanda Connect pipeline configurations as YAML files. Each YAML file should define a pipeline that you want to run in Redpanda Connect.

## Instructions

1. **Add your pipeline files**: 
   - Place your Redpanda Connect pipeline YAML files in this directory.

2. **Pipeline File Format**: 
   - Each pipeline YAML file should define a valid Redpanda Connect configuration.

3. **Running the Pipelines**: 
   - To ensure that your pipelines are launched correctly, the `docker-compose.yml` file uses the following command structure:
     ```yaml
     command:
       - sh
       - -c
       - |
         redpanda-connect run --log.level=TRACE /pipelines/pipeline1.yaml &
         redpanda-connect run --log.level=TRACE /pipelines/pipeline2.yaml &
         ...
         wait
     ```
   - This will run each pipeline configuration file in the background and wait for all of them to complete.

## Notes
- Ensure that each YAML file follows proper Redpanda Connect configuration syntax.
- If you need to add more pipelines, simply place additional `.yaml` files in this directory using meaningful names for each pipeline.

## Troubleshooting
- If a pipeline fails to launch, verify the syntax and correctness of the `.yaml` configuration.
- Logs will be available in the container to help debug any issues with pipeline execution.