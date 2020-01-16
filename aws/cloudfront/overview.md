
## Deliver
### How CloudFront Works with Regional Edge Caches
Regional edge caches help with all types of content, particularly content that tends to become less popular over time. 

### How Regional Caches Work
Regional edge caches are CloudFront locations that are deployed globally, close to your viewers. Regional edge caches have a larger cache than an individual POP. This helps keep more of your content closer to your viewers, reducing the need for CloudFront to go back to your origin server, and improving overall performance for viewers.
1. Viewer makes a request on your website or through your application, DNS routes the request to the POP that can best serve the user’s request.
2. In the POP, CloudFront checks its cache for the requested files.
2.1. If the files are in the cache, CloudFront returns them to the user.
2.2. If the files are not in the cache, the POPs go to the nearest regional edge cache to fetch the object.
2.2.1. In the regional edge cache location, CloudFront again checks its cache for the requested files. If the files are in the cache, CloudFront forwards the files to the POP that requested them. As soon as the first byte arrives from regional edge cache location, CloudFront begins to forward the files to the user. CloudFront also adds the files to the cache in the POP for the next time someone requests those files.
2.2.2. For files not cached at either the POP or the regional edge cache location, CloudFront compares the request with the specifications in your distributions and forwards the request for your files to the origin server
