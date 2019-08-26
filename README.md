Config file to build an algolia index over all frappe / erpnext documentation:

https://community.algolia.com/docsearch/config-file.html

Create a `.env` file in this directory: 

```
APPLICATION_ID=YOUR_APP_ID
API_KEY=YOUR_API_KEY
```

And let docker take care of the rest:

```bash
docker run -it --env-file=.env -e "CONFIG=$(cat config.json | jq -r tostring)" algolia/docsearch-scraper
```
