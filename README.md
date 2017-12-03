# Angular5 deploy to GAE

## docker build

```
docker build -t angular5 .
```

## docker run and npm install

```
docker run -it --rm -v $(pwd):/app angular5:latest /bin/ash

## container
cd app/my-project-name
npm install

```

## ng serve

```
docker run -it --rm -w /app -v $(pwd)/my-project-name:/app -p 4200:4200 angular5:latest ng serve --host 0.0.0.0
```

## ng build

```
docker run -it --rm -w /app -v $(pwd)/my-project-name:/app angular5:latest ng build --target=production --output-path=./service/static
```

## gcloud app deploy

```
export PROJECT_ID=PROJECT_ID
cd my-project-name/service
gcloud app deploy --project=${PROJECT_ID} app.yaml
```
