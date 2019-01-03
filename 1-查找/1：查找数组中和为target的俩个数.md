
```
public class Sum {

	// n²的常规方法
	public void two_num_oldway(int[] array, int length, int target) {

		for (int i = 0; i < array.length; i++) {

			for (int j = i + 1; j < array.length; j++) {
				// this position need to set i+1,otherwise it will repeat
				if (array[i] + array[j] == target) {

					System.out.println("two numbers\t" + array[i] + "\t" + array[j]);
				}
			}
		}

	}

	//  基于或先进行排序的
	//设置俩个指针，设置sum，如果sum大于target则右指针向左移动，小于向右移动，等于，输出，并且俩个都进行移动
	void two_sum_sorted(int[] array, int length, int target) {
		int left = 0, right = length - 1;
		while (left < right) {
			int sum = array[left] + array[right];
			if (sum > target)
				right--;
			else if (sum < target)
				left++;
			else {
				System.out.println("two numbers:" + array[left] + "\t" + array[right]);
				left++;
				right--;
				//注意这里不要忘了left++,right++
			}
		}
	}

	public static void main(String[] args) {
		Sum sum = new Sum();
		int[] array = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
		sum.two_num_oldway(array, 10, 15);
		sum.two_sum_sorted(array, 10, 15);

	}
}
```



---

---
基于哈希表的算法
（有待更新）