bff should be implemented by frontend team.

BFF is good for mobile, since mobile clients can have different versions.
what if there is new api, no emergency deployment.

backward compatibility


For an application that only provides one front-end, I suspect Backend For Frontend will only make sense if and when you have a significant amount of aggregation required on the server-side. Still, even then, the concept of API gateway can be used. BFF style can be considered when you plan to extend the number of frontend types.

shifting some front-end logic to an intermediate layer

If the request has to go through another component, it will definitely increase latency. However, the BFF latency is negligible compared to the browser’s high resource usage if it needs to work with multiple services not optimized for the frontend.

Building a BFF allows you to intelligently make batch calls to other backends/ microservices and return the data all at once

This can be very useful for mobile clients on 2G or 3G networks where it can take seconds (or more) to establish the connection.


-   **Separation of concerns** — Frontend requirements will be separated from the backend concerns. This is easier for maintenance.
-   **Easier to maintain and modify APIs** — The client application will know less about your APIs’ structure, which will make it more resilient to changes in those APIs.
-   **Better error handling in the frontend** — Server errors are meaningless to the frontend user most of the time. Instead of directly returning the error server sends, the BFF can map out errors that need to be shown to the user. This will improve the user experience.
-   **Multiple device types can call the backend in parallel** — While the browser is making a request to the browser BFF, the mobile devices can do the same. It will help obtain responses from the services faster.
-   **Better security** — Certain sensitive information can be hidden, and unnecessary data to the frontend can be omitted when sending back a response to the frontend. The abstraction will make it harder for attackers to target the application.
-   **Shared team ownership of components** — Different parts of the application can be handled by different teams very easily. Frontend teams get to enjoy ownership of both their client application and its underlying resource consumption layer; leading to high development velocities. The below diagram shows an example of such a team separation along with BFFs.