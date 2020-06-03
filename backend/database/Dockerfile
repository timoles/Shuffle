# 2. docker run -p 8000:8000 
FROM google/cloud-sdk 

EXPOSE 8000
CMD ["gcloud", "beta", "emulators", "datastore", "start", "--project=shuffle", "--host-port", "0.0.0.0:8000", "--data-dir=/etc/shuffle"] 
# CMD ["gcloud", "beta", "emulators", "datastore", "start", "--project=shuffle", "--data-dir=/etc/shuffle"] # TODO readd the , "--host-port", "0.0.0.0:8000", because otherwise the console is exposed

