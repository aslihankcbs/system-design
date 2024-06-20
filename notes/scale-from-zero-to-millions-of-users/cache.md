# Cache

**Definition:** Temporary storage area in memory for frequently accessed or expensive data.

**Purpose:** Enhances application performance by reducing database calls.

### Cache Tier:

A faster, temporary data store layer.

**Benefits:** Improves system performance, reduces database workload, and allows independent scaling.

**Operation:** Uses strategies like read-through cache to check cache first, then database if needed.

### Interacting with Cache Servers:

**APIs:** Commonly provided for various programming languages (e.g., Memcached APIs).

### Considerations for Using Cache:

**When to Use:**

* **Frequent Reads, Infrequent Modifications:** Suitable for read-heavy data.
* **Volatile Memory:** Not for persistent data; data is lost if cache server restarts.

**Expiration Policy:**

* **Importance:** Prevents permanent storage of outdated data.
* **Balance:** Avoid too short (frequent reloads) or too long (stale data) expiration periods.

**Consistency:**

* **Challenge:** Keeping data store and cache in sync, especially across regions.

**Mitigating Failures:**

* **SPOF:** Avoid single points of failure by using multiple cache servers.
* **Overprovisioning:** Allocate extra memory to handle increased usage.

**Eviction Policy:**

* Removing items when the cache is full.

* Common Policies:
  * Least-Recently-Used (LRU): Most popular.
  * Least Frequently Used (LFU): Another option.
  * First In First Out (FIFO): Alternative approach for different use cases.


## Content Delivery Network (CDN):

A network of geographically dispersed servers delivering static content.

**Static Content:** Caches images, videos, CSS, JavaScript files.
**Dynamic Content Caching:** caches HTML pages based on various parameters.

### How CDN Works:

- **User Request:** User requests content via a URL provided by the CDN.
- **Cache Check:** CDN server checks if the content is cached.
- **Origin Request:** If not cached, CDN server requests the content from the origin server.
- **Caching Content:** CDN server caches the content with a Time-to-Live (TTL) header.
- **Subsequent Requests:** Other users receive cached content if TTL has not expired.

### Considerations for Using a CDN:

- **Cost:**
  - **Third-Party Providers:** Charged for data transfers.
  - **Infrequent Assets:** Consider moving them out of the CDN to save costs.

- **Cache Expiry:**
  - **Time-Sensitive Content:** Set appropriate expiry times.
  - **Balance:** Avoid too long (stale content) or too short (frequent reloads) expiry periods.

- **CDN Fallback:**
   - **Outage Handling:** Ensure clients can request resources from the origin if the CDN fails.

- **Invalidating Files:**
  - **CDN APIs:** Use provided APIs to invalidate objects.
  - **Object Versioning:** Serve different versions by adding parameters to URLs (e.g., image.png?v=2).

- **Performance Improvement:**
  - **Static Assets:** Served from the CDN, not web servers.
  - **Database Load:** Reduced by caching data.