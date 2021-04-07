Association rule minning using Eclat

Prerequisites :- Association rule minning using Apriori https://github.com/mchaubey7/Association_rule_minning_or_apriori 

The ECLAT algorithm stands for Equivalence Class Clustering and bottom-up Lattice Traversal. It is one of the popular methods of Association Rule mining. It is a more efficient and scalable version of the Apriori algorithm. While the Apriori algorithm works in a horizontal sense imitating the Breadth-First Search of a graph, the ECLAT algorithm works in a vertical manner just like the Depth-First Search of a graph. This vertical approach of the ECLAT algorithm makes it a faster algorithm than the Apriori algorithm.

The basic idea is to use Transaction Id Sets(tidsets) intersections to compute the support value of a candidate and avoiding the generation of subsets which do not exist in the prefix tree. In the first call of the function, all single items are used along with their tidsets. Then the function is called recursively and in each recursive call, each item-tidset pair is verified and combined with other item-tidset pairs. This process is continued until no candidate item-tidset pairs can be combined.

In apriori to calculate the strength of association we calculate support, confidence and lift but in Eclat we only calculate the support. The calculation for the support in both algorithm is also different. 
In apriori the support is calculated in the following manner :
				
				Support(M) = Data_containing_M/Total_data
				Here M is one item.

In Eclat the support is calculated in the following manner : 
				
				Support(M) = Data_containing_M/Total_data
				Here M is not one item but pair or groups of item

				
Algorithm :
1. Set a minimum support for M, where is pair or group of items
2. Take all the subset in the dataset having higher support than the minimum support 
3. Sort these support in decreasing support.

				
Advantage of Eclat over apriori
1. Memory Requirements: Since the ECLAT algorithm uses a Depth-First Search approach, it uses less memory than Apriori algorithm.
2. Speed: The ECLAT algorithm is typically faster than the Apriori algorithm.
3. Number of Computations: The ECLAT algorithm does not involve the repeated scanning of the data to compute the individual support values.