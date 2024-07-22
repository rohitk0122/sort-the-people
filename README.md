# sort-the-people\
class Solution {
    public String[] sortPeople(String[] names, int[] heights) {
       int n = names.length;

        // Create a list of pairs where each pair contains a name and its corresponding height
        List<Person> people = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            people.add(new Person(names[i], heights[i]));
        }

        // Sort the list based on heights in descending order
        Collections.sort(people, (a, b) -> b.height - a.height);

        // Extract the names from the sorted list
        String[] sortedNames = new String[n];
        for (int i = 0; i < n; i++) {
            sortedNames[i] = people.get(i).name;
        }

        return sortedNames; 
    }

    // Helper class to store name and height pairs
    class Person {
        String name;
        int height;

        Person(String name, int height) {
            this.name = name;
            this.height = height;
        } 
    }
}
