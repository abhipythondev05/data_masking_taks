# Use an official PySpark base image
FROM bitnami/spark:3.5.0

# Install Python package manager and necessary utilities
USER root
RUN apt-get update && \
    apt-get install -y python3-pip && \
    apt-get clean

# Upgrade pip and install Python dependencies
RUN pip3 install --upgrade pip && \
    pip3 install pyspark faker pandas notebook

# Verify installation of Python packages
RUN python3 -m pip show notebook || echo "Jupyter not found" && \
    python3 -m pip show pandas || echo "pandas not found" && \
    python3 -m pip show faker || echo "Faker not found"

# Set environment variables for Spark
ENV SPARK_HOME /opt/bitnami/spark
ENV PATH $SPARK_HOME/bin:$PATH

# Copy your notebook to the container
COPY ./masking2.ipynb /opt/notebooks/masking2.ipynb

# Create working directory for temporary local CSV storage
RUN mkdir -p /tmp/local_csv_files

# Set the working directory
WORKDIR /opt/notebooks

# Expose port 8888 for Jupyter
EXPOSE 8888

# Start Jupyter Notebook
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--allow-root", "--no-browser", "--NotebookApp.token=''"]

