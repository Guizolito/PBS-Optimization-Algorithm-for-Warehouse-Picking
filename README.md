# Warehouse-Picking-Time-Calculator

This project originated from a University class with the main challenge being to strategize a Warehouse product layout, Inbound + Outbound positions, picking strategy in the dispatch area in order to minimize total costs while keeping the same service level to stores.

Data on the current SKUs and respective stock levels, optimal pallet content, picking data and overall cost and time characteristics of the picking procedures were provided. Due to privacy concerns, this data will not be shared on this repository.

For product layout, an ABC analysis was made using the current stock levels and orders to determine the SKUs with higher turnovers closer to the outbound and the one with lower turnovers in the outer part of the Warehouse. Some C references were introduced alongside B references given the "bundle" phenomenon - several products that are ordered together frequently. This would save some time, avoiding having to cross the whole Warehouse to pick certain C-types.

For the picking algorithm, a hybrid between 3 strategies was used, (calculating the optimal combination between the 3) namely:

# S-shape strategy
The order picker collects the products according to the so-called S-shape (or traversal) strategy. The S-shape strategy is often applied in practice, because of its simplicity, which makes it easy to understand and to use. In this strategy, any aisle containing at least one item is traversed over the entire length except possibly for the last pick aisle. Aisles with no picks are skipped.

# Midpoint strategy
Take the same warehouse as depicted in Figure 1. This time the order is picked according to the so-called midpoint strategy. For this method the warehouse is divided into two halves. Picks in the front half (depot side) are accessed from the depot (=right) side and picks in the back half are accessed from the opposite (=left) side. Only the first and the last pick aisle are traversed entirely provided there are picks on the left side.

# Largest gap strategy
The order picker enters an aisle until he/she reaches the largest gap within that aisle. A gap represents the distance between any two consecutive picks, between the first pick and the beginning of the pick aisle, or between the last pick and the end of the pick aisle. The largest gap is the part of the aisle that is not visited by the order picker. If the largest gap is between two consecutive picks, the order picker performs a return route from both ends of the aisle. Otherwise, a return route from either the depot side or the opposite side is performed. In case the opposite side (seen from the depot) is accessed then both the first and the last pick aisle are traversed.

According to time per picking, forklift speed and the remaining associated costs, an estimate is calculated in the end. All values mentioned in the code are ficticious due to privacy concerns.
