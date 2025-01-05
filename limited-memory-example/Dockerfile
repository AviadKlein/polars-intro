# Use an official Python image as the base
FROM python:3.10-slim

# Ensure apt-get is up to date and install needed packages
RUN apt-get update && apt-get install -y \
    wget \
    gnupg \
    curl \
    # For Chrome, you need some dependencies:
    fonts-liberation \
    libatk-bridge2.0-0 \
    libatspi2.0-0 \
    libgtk-3-0 \
    libdrm2 \
    libgbm1 \
    # If you'd rather install Chromium (open-source Chrome), you can do so with:
    chromium \
    # That’s it for Chromium. 
    # If you truly want "Google Chrome," read the note below.
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install Jupyter
RUN pip install --no-cache-dir jupyter

# Expose port 8889 for Jupyter
EXPOSE 8889

# By default, run Jupyter Notebook
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8889", "--no-browser", "--allow-root"]

