# Supply_Planning_CaseStudy
Supply Planning Case Study for Food Factory, resolve demand forecast problem by MRP, DRP, MPS\
Festory is a factory specializing in producing animal feed headquartered in BD, in which animal feed for pigs and fish are the two main products that bring a large source of revenue to the factory. Since 2020, realizing the increased demand for sheep and chicken feed in the DNB and MT areas, Festory has deployed the construction of Festory II with 2 specialized lines to boost production capacity of the two products. STAR SHEEP (sheep feed) and WOW CHICKEN (chicken feed) to promptly meet customer needs. Each type is produced in two packaging types: 25kg bag and 40kg bag. \
Festory II currently has more than 1,000 workers working from Monday to Saturday (closed on Sunday). Every day, a worker works 2 shifts of 6 hours/shift and the factory does not apply overtime to workers. With technical investment Techniques and technology, a STAR SHEEP line can produce 2 tons/day while a WOW CHICKEN line can produce 3 tons/day.
To meet current storage needs, in addition to the factory warehouse currently used to store raw materials and temporarily store finished products, Festory II also rents additional warehouses in BD to serve customers in DNB and warehouses in CT. (Tra Noc Industrial Park 2) specializes in serving customers in MT. It is known that goods are not transferred between warehouses and customers do not receive goods on Sundays. During the week, the factory only makes deliveries
Goods delivered to BD warehouse will arrive on Monday and Wednesday, while goods delivered to Can Tho warehouse will arrive the next day. From May onwards, goods cannot be stored for more than 30 days, applicable to finished goods at BD and CT warehouses. Particularly for factory warehouses, the maximum storage time is 30 days for raw materials and 10 days for finished products. Safety stock calculated based on working days for finished products at BD and CT warehouses is 2 and 3 days, respectively, and for raw materials at the factory warehouse is 10 days.
It is known that on average 70% of deliveries (demand) belongs to the last 14 calendar days of the month. At the present time, March 31, 2023, the factory records demand from customers from the INPUT_DEMAND sheet as follows:
 ![image](https://github.com/Desnyyy/Supply_Planning_CaseStudy/assets/88900307/1b858edf-ce6d-45bd-9518-6039a9b51ae3)

 ![image](https://github.com/Desnyyy/Supply_Planning_CaseStudy/assets/88900307/40923427-b986-4ae6-8567-ee9dfb60eee1)

The animal feed production process at Festory II is guaranteed to meet safety standards with high requirements in terms of quality and handling. Normally, an animal feed product will be created from basic ingredients such as corn, potatoes, cassava, probiotics... with the assumption of loss during production and storage of raw materials. is 2% except packaging. At the same time, materials with more than 50% shelf life will not be put into production except for packaging. Material details of the 2 types of products (Bill of Material) are provided in sheet INPUT_BOM with the sample structure of STAR SHEEP 25KG as follows:

 ![image](https://github.com/Desnyyy/Supply_Planning_CaseStudy/assets/88900307/b882bef9-1f57-4f2c-b541-fcc984c2c282)

At the end of March 31, 2023, Festory II's warehouse conducted statistics and recorded a number of raw materials in the warehouse (Stock on hand) as well as received a report on the quantity of goods currently in the two warehouses Binh Duong and Binh Duong. Can Tho according to sheet INPUT_SUPPLY_SOH as follows:

![image](https://github.com/Desnyyy/Supply_Planning_CaseStudy/assets/88900307/de146a0c-7419-42d5-bed3-e9e1e9587885)
![image](https://github.com/Desnyyy/Supply_Planning_CaseStudy/assets/88900307/5fb0df2c-c8a0-45a3-9225-67c14ddc2f9c)
![image](https://github.com/Desnyyy/Supply_Planning_CaseStudy/assets/88900307/bef66866-8afd-4618-9fe3-84f93428e662)
![image](https://github.com/Desnyyy/Supply_Planning_CaseStudy/assets/88900307/e0d8edea-e160-4d48-a567-6e3ea1933961)


In addition, Ongoing supply orders for Raw Materials are known to arrive in warehouses in the first week of April 2023. Ongoing supply information is provided in the INPUT_SUPPLY_ONGOING sheet as follows:
 ![image](https://github.com/Desnyyy/Supply_Planning_CaseStudy/assets/88900307/125964ad-e28a-474b-a027-b2213c867b4f)

Know that finished products with less than 50% shelf life will not be delivered to customers and at this time (March 31, 2023) there are no shipments being delivered from the factory to the warehouses.
Festory II is currently negotiating with the Supplier to order materials according to MOQ (Minimum order quantity) rules with specific data provided in sheet INPUT_ITEMASTER. In particular, WOPACK COMPANY LIMITED does not require MOQ for each Item but for each PO (Purchase Order), each PO has a minimum of 1000 pieces. In addition, the leadtime of raw materials and products is provided as follows.
![image](https://github.com/Desnyyy/Supply_Planning_CaseStudy/assets/88900307/f3ef2602-6d59-40d9-b71e-18cb2308e827)
![image](https://github.com/Desnyyy/Supply_Planning_CaseStudy/assets/88900307/3554c84c-bd9b-45c2-8d61-b307d3367ea0)

 
Currently, the factory side is storing data on three different platforms. Specifically, information about INPUT_DEMAND and INPUT_SUPPLY_SOH is saved on
Google Sheet is intended to be conveniently and easily accessible to both demand planning and warehouse departments. Information about INPUT_BOM and INPUT_ITEMMASTER is stored on the specific ERP system in the factory's SQL database to ensure data integrity. Particularly for information about INPUT_ONGOING, because the factory must send data to the supplier, the data is currently stored as an offline excel file for each PO.
Based on the information provided, the team as Supply Chain Manager should:
1. Determine the quantity of raw materials to order according to MOQ to ensure the most optimal operating and production process.
2. Determine production plans and transfer goods from the factory to warehouses (if any)
3. Determine the amount of finished products or raw materials at risk of expiration (if any)
