import sys
import googler
from result_item import ResultItem

def search(query):
    # Prepare a list for returning the search results
    result = list()
    # Initialization for googler
    opts = googler.parse_args()
    repl = googler.GooglerCmd(opts)
    # Googler fetches the search result page
    repl.fetch()
    if not repl.results:
        print('No results.')
    else:
        # Extract and pack the search results into the list if items exist
        for r in repl.results:
            result.append(ResultItem(r.title, r.url))
    # Return the result list
    return result

# Main Function
if __name__ == "__main__":
    #Prepare query variable
    query = sys.argv[1]
    # Append multiple query words with "+"
    for arg in sys.argv[2:]:
        query = query + "+" + arg
    # Experiment the search function
    result = search(query)
    # Print the result list to the command line
    for item in result:
        print("[title] "+item.title)
        print("[url] "+item.url)
