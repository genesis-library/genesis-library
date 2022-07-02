go vs nodejs?
when payload gets bigger, will it cause to make the request slow or consumes bandwidth?

https://stackoverflow.com/questions/57852689/kafka-msg-vs-rest-calls


1.  -   **Kafka** - Publish & Subscribe (just process the pipeline, will notify once the job is done)
        
    -   **REST** - Request & Await response (on-demand)
        

---

2.  -   **Kafka** - Publish once - Subscribe _n_ times (by _n_ components).
        
    -   **REST** - Request once, get the response once. Deal over.
        

---

3.  -   **Kafka** - Data is stored in topic. Seek back & forth (_offsets_) whenever you want till the topic is retained.
        
    -   **REST** - Once the response is over, it is over. Manually employ a database to store the processed data.
        

---

4.  -   **Kafka** - Split the processing, have intermediate data stored in intermediate topics (for speed and fault-tolerance)
        
    -   **REST** - Take the data, process it all at once OR if you wish to break it down, don't forget to take care of _your OWN_ intermediate data stores.
        

---

5.  -   **Kafka** - The one who makes the request _**typically**_ is not interested in a _response_ (except the response that if the message is sent)
        
    -   **REST** - I am making the request means I _**typically**_ expect a response (not just a response that you have received the request, but something that is meaningful to me, some computed result for example!)