# Intro into `polars`

## Example on NYC cab data

Download the data from: https://www.kaggle.com/competitions/nyc-taxi-trip-duration

The main notebook is `intro to polars.ipynb`.
Written on `Python 3.12.4`.

## There is an example for a small machine with limited memory
to run it:
1. Install Docker.
2. Build the docker from the main directory of this project. The Dockerfile points to port 8889 so make sure it's not hosting anything else and if so make sure to change it.
```bash
docker build -t lim-mem-example limited-memory-example/
```
3. Run the docker, you can change the memory settings, since the file :
```bash
docker run -it --rm \
    --memory="500m" \
    --memory-swap="500m" \
    -p 8889:8889 \
    -v ~/Documents/learning/Intro\ to\ polars/limited-memory-example:/home/jovyan/work \
    lim-mem-example
```
4. Open up `localhost:8889` on your chrome and run the example
