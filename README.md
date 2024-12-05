# Exploring Recent Shootings in Philadelphia

This repository includes an example dashboard exploring recent shootings in Philadelphia,
using the City of Philadelphia's [open data on shooting victims](https://www.opendataphilly.org/dataset/shooting-victims).

The dashboard includes a slider widget that allows the user to specify how many days
into the past to display.

The dashboard includes:

- an Altair bar chart showing a histogram of the age of shooting victims, colored by fatal vs. non-fatal shootings
- a Folium heatmap of the shootings across the city
- an hvplot line chart showing the daily number of shootings, which can be filtered to view data for a specific time period



## Deploying this app on Hugging Face

This section describes how to deploy a Panel app to Hugging Face. See the [Panel documentation](https://panel.holoviz.org/how_to/deployment/huggingface.html) for additional info.

Hugging Face makes deployment of arbitrary apps including Panel apps and dashboards very easy and provides a free tier to get you started. This makes it a great starting point for users not too familiar with web development and deployment.

To get started, click on the following URL:

[https://huggingface.co/new-space](https://huggingface.co/new-space)

Once you load the above page, select the "Docker" Space SDK and then select the "Panel" template below it.

This will create a new "space" (like a GitHub repository) on 
your Hugging Face account and deploy an example Panel dashboard. It will add code for the dashboard to the `app.py` file in the space. If you don't have an account yet, it will prompt you to sign up when you click on the link below.

We can edit the template files in the browser to deploy our own dashboard instead of the example dashboard. 
Navigate to the "Files" tab in the space and we'll modify these files so our own dashboard will deploy.

Here are the steps involved:

1. Upload a "requirements.txt" file that includes all of the requirements for your project. Hugging Face will install these dependencies using `pip`.

2. Upload your Panel dashboard Jupyter notebook. For example, in this repository I uploaded "shootingApp.ipynb".

3. Edit the "Dockerfile". By default, it serves the panel dashboard in "app.py". Change "/code/app.py" in the Dockerfile to the name of the notebook you uploaded in step #2. For example, for this repository, I changed it to read: "/code/shootingApp.ipynb".

That's it! You should see your app "Building" and then "Running" in the Hugging Face UI. 
If there's an issue during installing the packages in your "requirements.txt", you'll see a "Build error"
or "Runtime error". You can check the log output to see what went wrong and try to debug.  

If everything worked, you can click on the "App" tab next to the "Files" tab to view your app! 
