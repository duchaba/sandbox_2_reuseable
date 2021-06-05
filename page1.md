# 1. Introduction

**Start Here!**

Welcome to the GraphQL journey. Are you smiling? 😀 

If you're curious about GraphQL, then the "Introduction" is all you need to read. The goal for the "Introduction" is to describe GraphQL for techie and non-techie alike.

If you're a nerd or a nerd at heart, then shoulder forward. The content will be more technical in later chapter.

---

 

### A. Quick Introduction

GraphQL is a relatively new technology for mobile phone apps, tablets, and websites to request information from the backend server. 

![1%20Introduction%20a332212e3ede4afebb7535a4f2ec2279/Screen_Shot_2021-06-04_at_12.10.48_PM.png](1%20Introduction%20a332212e3ede4afebb7535a4f2ec2279/Screen_Shot_2021-06-04_at_12.10.48_PM.png)

The big breakthrough is different clients can request different data using the same API endpoint from the server. In the old days, the server responds with the same data for everyone. That's it, but don't stop reading.

---

### B. Analogy and Examples

As an analogy, in the old days, when buying a pizza, you can choose a frozen Pepperoni, Cheese, All-meat, Veggie, or Southern Carolina BBQ Bonanza pizza. Each frozen pizza comes with a set of ingredients that you can't change. For example, you can't buy a veggie pizza with no cheese and no broccoli or order a "thin crust, provolone cheese, tomato source with prosciutto and bell peppers" pizza. 

The breakthrough is you can choose what on your pizza. For example, you can add wild mushroom to your pepperoni pizza or design your perfect late-night pizza. 

![https://images.unsplash.com/photo-1585238342024-78d387f4a707?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb](https://images.unsplash.com/photo-1585238342024-78d387f4a707?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb)

---

A more common API example is requesting users information. 

- **In the old days, request using REST API and response in JSON**

```json
[REQUEST]

~/yml/employee/q123456
```

```json
[RESPONSE]

{
	id: "q123456",
	name: "Duc Haba",
	projects: [
		{
			client: "Kaiser Permanente",
			location: "CA"
		},
			client: "Garden World",
			location: "Switzerland",
		},
		{
			client: "AI Foundation",
			location: "Hawaii"
	],
	age: 25,
	role: "TPO/Solution Arch"
	shoe: 8.5
	address: "12 home",
	city: "Fremont",
	zipcode: "94536",
	hobbies: [
		"gardening",
		"swimming",
		"traveling",
	],
	office: "Redwood Shores",
	covid_19: "vaccinated",
	building_key: "p9876543",
	avail_vacation_day: 31,
	blood: "B-",
	insurance: "Kaiser Permanente",
	doctor: "Dr. Donald Duck"
}
```

- It is the same request API endpoint and the same response JSON for everyone. Therefore, each app or website must write the logic to parse the standard response JSON separately.

- **A new way, request using GraphQL and response JSON**

```json
[REQUEST]

~/yml/employee

query {
	Employee(id : "q123456") {
		name,
		city,
		hobbies
	}
}
```

```json
[RESPONSE]

{
	"data" : {
		"Employee" : {
			"name" : "Duc Haba",
			"city" : "Fremont",
			"hobbies" : [
				"gardening",
				"swimming",
				"traveling"
			]
		}
	}
}
```

- With GraphQL, other apps, websites, or emails can customize their request differently using the same endpoint.

```json
[REQUEST]

~/yml/employee

query {
	Employee(id : "q123456") {
		name,
		office,
		role,
		insurance,
		doctor,
		covid_19,
		projects(first: 1) {
			client
		}
	}
}
```

```json
[RESPONSE]

{
	"data" : {
		"Employee" : {
			"name" : "Duc Haba",
			"office" : "Redwood Shores",
			"role" : "TPO/Solution Arch",
			"insurance" : "Kaiser Permanente",
			"doctor" : "Dr. Donald Duck",
			"covid_19" : "vaccinated",
			"projects" : [
				{ "client" : "Kaiser Permanente" }
			]
		}
	}
}
```

- The users choose which data fields to request. In other words, the users can add or remove data fields without waiting for the backend to recode.

---

### C. Benefits and History

> So, why is an option to choose a big breakthrough?

For non-techie, it may sound like "common sense." Freedom to choose is better than taking what the G-man is giving you. But for the techie, that is not how we used to do things. "I love frozen pizza, don't take that away from me." 😋

 The benefits are many. Chief among them is faster, more agile development cycles, cleaner code, fewer bugs, reduced system load, and a path to omnichannel. 

The benefits come with a cost. For enterprise companies, moving from REST API to GraphQL is a substantial investment. It takes a lot of time, resources, and funding. In addition, it will have a high-risk factor for failure, but it is a technical debt with accrued compound interest. The sooner you address the issue, the lesser the cost.

Reusing the same pizza analogy, retrofitting a frozen pizza factory to a customer responsive pizza emporium wonderland is not easy.

Facebook developed GraphQL in 2012 originally to work with ReactJS. It public released is in 2015 and move to open-source GraphQL Foundation in 2018, and the Linux Foundation hosted it.

![1%20Introduction%20a332212e3ede4afebb7535a4f2ec2279/Screen_Shot_2021-06-04_at_10.35.36_AM.png](1%20Introduction%20a332212e3ede4afebb7535a4f2ec2279/Screen_Shot_2021-06-04_at_10.35.36_AM.png)

---

### D. Next Step

That is all you need to know for GraphQL. If you a nerd or a nerd at heart, go to the next chapter. It will be more technical and with more "dad" jokes. 

The next chapter is "[2. GraphQL .vs. REST API ( ✅ )](http://google.com)." If you're a PM, you might want to skip to chapter "8. KP Implementation ( ❤️‍🩹 )" to see how an enterprise company is doing it and the lesson learned.