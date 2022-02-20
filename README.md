# treehacks2022

disclaimer: we didn't have enough time during the video demo to talk about everything we made for our project and explain our idea in detail so here's a thick 📕 for you to read if you're interested oop!

## Inspiration 💡
While discussing the recent cold weather in Vancouver, our friend Ryan remarked that he was keeping himself warm by mining cryptocurrency. After some light Google searching, we found out that it may be possible to leverage this idea in locations outside of his parents' basement. 

##Initial Research 🔎
What we found out is that there are places where the heat generated by computers would not be considered a feature, but a useless byproduct. For example, cooling can be up to 40% of a data center’s total energy usage. Large bitcoin farms are experiencing the same issues, employing fans and air conditioners to move heat away from their devices. 

##Problem 💭
Is there a way to reduce cooling loads by redistributing this heat to people who need to make these technologies more sustainable?

##What is the Box with Rounded Corners? 📦
The _Box with Rounded Corners_ (_The Box_ in short) is a platform where cryptocurrency miners could be used to provide free heating for small businesses. It consists of a custom-designed cryptocurrency mining rig, a smart thermostat system, and a data visualization platform powered by AI and ML to allow business owners to heat up their spaces more efficiently and effectively. 

_The Box_ is a 3d printed housing that stores computing hardware required to mine crypto. William custom-designed an ASIC chip that accelerates sha256 hashing. This design was made using Google’s open-source SkyWater PDK and we hope to realize it into silicon if possible. In the future, this computing box will work in conjunction with energy storage hardware. 

_Therma_, another part of our product, is a smart thermostat. _Therma_ communicates with the box to control heating. By setting _Therma_ higher, _The Box_ will provide computing power or mine crypto. It uses **Mage** to predict ML models for determining which heating source is most efficient depending on external factors like predicted crypto price, past weather trends, and carbon footprint of the electricity source.

Christy created a dashboard that helps the user visualize what happens within their _Boxes_ and how it impacts the user. The main page shows stats for daily usage, an overview of monthly usage, crypto mined, as well as a comparison between using crypto mining (renewable energy resources) vs fossil fuels to heat up their space. There are also many other tabs that allow the user to control which of their boxes should be actively mining, more robust visualizations of environmental impact using **VMWare’s Wavefront**, regulation of temperature through **Mage’s ML model predictions**, and more of the costs and earnings breakdown. There is also a donation option that encourages users to donate to offset their carbon footprint.

We initially started our project by doing visualizations with graphs and diagrams from MUI. However, we pivoted to using **VMWare’s Wavefront** after discovering how comprehensive and informative the graphs were for our users. We wanted to really showcase the sustainability factor of the _Box with Rounded Corners_ product to encourage greener mining so it was useful for us to be able to highlight the data around environmental impact. While developing our product, we thought it would be amazing to have a way to share the dashboard without logging in.

Our product uses **Mage** to train all our machine learning models to come up with predictions for when is the most efficient and effective time to mine crypto/increase room temperature, as well as predicting when there would be an excess of cleaner/renewable energy (ie. certain hours of the day have more energy generated from windmills) to mine more crypto. We were extremely amazed at how easy it was to train a model on the platform because one of us had no machine learning experience before. However, we did wish it could be more customized and allow for fine adjustment of parameters.

##Advantages for Small Businesses 👍
By using the _Box with Rounded Corners_, small businesses can be reimbursed for their energy usage, while lowering their heating bills. 43% of a small businesses’ energy usage is actually dedicated to space heating. 

##Theoretical Savings 💾
In 2019, bitcoin mining consumed 111.7 terawatt-hours of power, or roughly equivalent to the power consumption of the Netherlands. If we were to assume a conservative savings estimate of 20% due to the reduction of cooling loads, the _Box with Rounded Corners_ could theoretically provide a savings of 11.17 terawatt-hours per year if 50% of all bitcoin miners were to switch to our platform. The energy saved constitutes a reduction of 4.75 million tons of CO2  emissions per year and is enough to power 434,724 households for a year.

[How Bitcoin's vast energy use could burst its bubble - BBC News](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=2510006001)
https://www.eia.gov/tools/faqs/faq.php?id=74&t=11

## How We Built It 🔨
The smart thermostat communicates with the box via an esp32 over wifi. _The Box_ hosts a local copy of the backend server that talks with the **Mage** Api for our ML needs. The box also hosts the dashboard which provides visualization in conjunction with **VMWare**. We also designed 3d models of our _Box_ and _Therma_ products using SolidWorks and printed them out using a 3d printer.

## About the Hardware 🔌
We built several hardware projects to actualize our project. The smart thermostat “Therma” was created using an esp32 for the brains, which connects over wifi to the box. The esp32 controls relays to interface with existing heating networks while also providing an interactive display to display the status of the home. It also sends temperature data to the box for further processing. Unfortunately, due to shipping delays we were not able to add occupancy sensors to the thermostat which would give our ML models more data to create a better prediction. On a side note, the green cover plate is 3d printed in glow in the dark filament so changing the temperature in the dark of night will be a problem of the past. 

We also designed and tested an ASIC meant to accelerate sha256 hashing. This design was heavily inspired by [Joachim Strömbergson’s](https://github.com/secworks) design and was truly an interesting project. This chip is meant to be included in the box to increase the efficiency and speed of crypto mining. This is similar to how purpose-built crypto miners are made and we would love to learn more. 

## Challenges We Ran Into 🔥
Our biggest challenge was trying to build Web 3.0 using Web 2.0 technologies. Some of the challenges we faced were hardware-related. Our 3d printer experienced clogging issues, bed adhesion problems, and the filament was too old so we had to reprint our parts four times in total. Additionally, we did not have any experience working with sha256 hashing so there was a steep learning curve to understand how to design the ASIC chip. On the software end, there was some difficulty cleaning up datasets so the trained models had realistic predictions. 

## Accomplishments We're Proud Of 🌟
We are extremely proud of what we were able to accomplish during this hackathon. We have been each other’s hackathon buddies for a while now but we’ve never been able to build and develop so much within a weekend before. We are particularly proud of being able to understand each others’ strengths and weaknesses so we could help each other out and teach one another new things during the project. William learned a lot about sha256 hashing while Christy finally tried machine learning for the first time! 

## What's Next ▶️
Our final goal is to realize a network of decentralised edge servers capable of running applications on demand. This would involve creating a network of boxes that can communicate and distribute applications like IPFS but for applications. The final form of our network would be able to provide decentralised edge computing to any application that would want to be both decentralised and sustainable.  

We would also love to build out the energy storage hardware. This would involve building and testing a battery pack that will safely charge and discharge to supplement the grid. It would also involve building the ML algorithms needed to accurately predict when to charge and discharge the batteries so it is not only sustainable but also provides redundancy to the grid.

Aditionally, we would love to see if our ASIC chip actually works. To achieve this we would send our design to a foundry like TSMC (we need a formal verification of the chip prior to this). With the limited time of a hackathon, only a very basic test suite was performed on the chip. 

With the creation of our platform, this would create a robust, decentralised, and sustainable computing network available everywhere for everyone to use. 

##Ethics 🌈
Cryptocurrency has been at the forefront of criticism through its ethical and environmental impact. A single bitcoin transaction alone burns approximately 2,292.5 kilowatt-hours of energy - enough to power a house for 78 days. The environmental cost of cryptocurrency is what steers potential Web 3.0 users away, driving an ever-expanding digital divide. Because of these reasons, we believe that the excess waste created from cryptocurrency mining is ethically unsustainable for the future. Although efforts have been made using technologies such as renewable energy, this does not solve the issue of the core byproducts of cryptocurrencies, such as e-waste and waste heat. 

Our team has proposed to relocate this waste, specifically the thermal energy created by cryptocurrency miners, to heat small businesses at a reimbursed cost. _Box with Rounded Corners_ strives to empower small businesses while offsetting the environmental impact of crypto mining through our dedicated platform. We plan on creating opportunities for users to invest these earnings into environmental organizations to empower positive impact within their own communities. While we acknowledge and identify that by providing a more sustainable solution to mining, we are also in turn promoting the use of cryptocurrency. Intermediate environmental costs such as the amount of energy needed to produce, buy and add products to the blockchain are high and our solution does not directly tackle this preliminary step. By adding a ‘safety net’ solution with our heat relocation, we are still enabling users to mine more cryptocurrencies and continue to contribute to energy waste. 

While crypto mining is inevitable, it’s important to acknowledge additional ethical implications other than just the environmental cost connected to the purpose of our organization. 

Targeting small business owners as our user base can be intimidating especially in the midst of the digital gap and the new concept of cryptocurrency. We recognize that there may be many business owners who may not trust the viability of our product and assume ulterior motives. Our team attempts to alleviate user experience by supplying small business owners with all the tools and transparency needed to boost confidence in utilizing our products. With our dashboard and familiar functionalities, users of all skill levels have been considered when implementing the UI by creating comprehensive labels and transparent data visualization while following WCAG3 standards. 

It is the intention of _Box with Rounded Corners_ to use smart contracts and blockchain technologies to ensure that no parties can alter any details within the agreement. While this will cause some environmental impacts due to the energy required to add to the blockchain, we will strive to minimize this impact while maintaining trust between our company and our users.

In the future, we hope to tackle our ethical concerns by conducting user research. It’s important for us to pinpoint the exact needs, behaviors, and pain points of our users in order to find the best solution - instead of just prescribing one. 
