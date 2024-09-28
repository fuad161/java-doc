# java-doc

https://dev.java/learn
public List<List<Integer>> subsets(int[] nums) {
        List<Integer> tmp = new ArrayList<>();
        List<List<Integer>> result = new ArrayList<>();
        dfs(0, nums, tmp, result);
        return result;
    }

    private void dfs(int index, int[] nums, List<Integer> tmp,  List<List<Integer>> result) {
        // base case
        if (index == nums.length) {
            // add to result
            result.add(new ArrayList<>(tmp));
            return;
        }

        // add
        tmp.add(nums[index]);
        dfs(index + 1, nums, tmp, result);
        tmp.remove(tmp.size() - 1);

        // not add
        dfs(index + 1, nums, tmp, result);
    }