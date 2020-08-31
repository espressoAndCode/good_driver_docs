**Drivers:**
-	earn points for good driving behavior
-	are affiliated with one sponsor company
-	use their points to purchase products from their sponsor's product catalog
-	points are added on a recurring basis for good performance
-	can use their points at any time for items in the sponsor’s catalog

**Sponsor Company:**
-	sponsor companies maintain a catalog of incentive products (G or PG only)
-	the products in the catalog must be selected by a means that allows for automated updating of the price and availability information of each item
-	product information must come from a publicly accessible Web API
-	sponsors set the dollar value of the driver points, the default value is $0.01 for each point

**Application Development Company (aka your team):**
-	all products are sold & delivered via a third party
-	receives 1% of total dollar value of point redemptions each month

**The incentive program app:**
-	uses an online API to produce the company specific catalog of incentive products (eg, eBay, Amazon, Overstock & etsy have them)
o	product availability
o	price
o	description
o	images of the product, offers, offer availability
o	other relevant information
 
-	uses the API to obtain the current product price before a product is added to the driver’s purchase set
-	the product catalogs are updated daily via the web API
 
**General:**

The incentive program app must be a responsive and conform to the size of the user’s display.
The sensitive data in the system (such as passwords) must be properly protected.
There should be a password reset system for the driver and sponsor users when they forget their password.
The system must be deployed to a publicly available server using a cloud hosting environment such as Azure, AWS or Google.
Professional Showcase
The team must select an area to go deeper, outside the requirements specified above. This must include one of the following:
- Database: use triggers, stored procedures, database jobs, user level access permissions
- Security: site hardening, penetration testing
- Testing: automated testing
- Mobile app: native iOS or Android app
- Deployment: automated deployment (eg, Azure pipelines or AWS Deploy)
- AWS: incorporate other AWS services

Your team’s professional showcase must be identified in your team summary.
Your team will need to provide a summary and artifacts to illustrate the team’s showcase as part of the final project demo.
