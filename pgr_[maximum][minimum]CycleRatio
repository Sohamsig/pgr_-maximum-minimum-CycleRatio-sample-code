#include <iostream>
#include <vector>
#include <boost/graph/adjacency_list.hpp>
#include <boost/graph/howard_cycle_ratio.hpp>

using namespace boost;

int main() {

    typedef adjacency_list<
        vecS, vecS, directedS,
        no_property,
        property<edge_weight_t, double>
    > Graph;

    Graph g(4);

    auto w = get(edge_weight, g);

    add_edge(0,1,3.0,g);
    add_edge(1,2,2.0,g);
    add_edge(2,3,4.0,g);
    add_edge(3,1,1.0,g);

    auto vim = get(vertex_index, g);

    std::vector<graph_traits<Graph>::edge_descriptor> max_cycle;
    std::vector<graph_traits<Graph>::edge_descriptor> min_cycle;

    double max_ratio = maximum_cycle_ratio(g, vim, w, w, &max_cycle);
    double min_ratio = minimum_cycle_ratio(g, vim, w, w, &min_cycle);

    std::cout << "Maximum Cycle Ratio: " << max_ratio << std::endl;
    std::cout << "Minimum Cycle Ratio: " << min_ratio << std::endl;

    return 0;
}
