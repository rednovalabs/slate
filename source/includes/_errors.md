# Errors

<aside class="notice">
  Specific api error codes are labeled with the <code>error_code</code> key.
</aside>

FmsAPI V2 uses the following error codes:


HTTP Error Code | API Error Code | Meaning
---------- | -------- | -------- |
**400** | **3** | **Bad Request** The requested action could not be performed.
**400** | **4** | **Bad Request** At least one parameter was missing or did not match validation criteria
**400** | **5** | **Bad Request** The supplied parameters conflict with one another.
**400** | **6** | **Bad Request** Reservations cannot be unreserved. Please close this lead and create a new one or contact the facility.
**400** | **7** | **Bad Request** The requested action has been disabled for tenants.  Please visit the facility for more information.
**400** | **8** | **Bad Request** The login and/or password provided was incorrect.
**400** | **10** | **Bad Request** Either the sort parameter you specified is not supported, or this resource does not support sorting.
**400** | **11** | **Bad Request** The tenant account you are trying to register already has an account setup.
**400** | **12** | **Bad Request** The refund requested has already been voided.
**401** | **2** | **Unauthorized** Invalid OAuth Request.
**403** | **13** | **Forbidden** The client does not have access rights to the requested content.
**404** | **9** | **Not Found** The resource you requested could not be found.
**405** | | **Method Not Allowed**
**406** | | **Not Acceptable**
**410** | | **Gone**
**418** | | **I'm a teapot**
**429** | | **Too Many Requests**
**500** | **1** | **Internal Server Error** Unknown API error. Sorry.
**503** | | **Service Unavailable**
