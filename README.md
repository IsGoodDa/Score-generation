以下是Java代码的一个示例；The following is an example of Java code：


import java.util.HashMap;

import java.util.Map;

public class ScoreGenerator {
    private Map<String, Integer> scores;

    // 构造函数
    public ScoreGenerator() {
        scores = new HashMap<>();
    }

    // 添加或更新评分
    public void addScore(String category, int score) {
        if (scores.containsKey(category)) {
            int oldScore = scores.get(category);
            scores.put(category, oldScore + score);
        } else {
            scores.put(category, score);
        }
    }

    // 获取总评分
    public int getTotalScore() {
        int total = 0;

        for (int score : scores.values()) {
            total += score;
        }

        return total;
    }

    // 获取指定类别的评分
    public int getScoreByCategory(String category) {
        return scores.getOrDefault(category, 0);
    }
}
