第一次編譯成功
執行時間為 2.313482 sec

接下來發現在 math-toolkit.h 這個檔案裡發現 dot_product這個function中
for迴圈不是必要的存在，for的指令反而會增加程式執行時間

    double dot_product(const double *v1, const double *v2)
    {
        double dp = 0.0;
        for (int i = 0; i < 3; i++)
            dp += v1[i] * v2[i];
        return dp;
    }

於是我將for迴圈展開，改成以下這樣

    dp += v1[0] * v2[0] + v1[1] * v2[1] + v1[2] * v2[2];

重新編譯後執行時間變為 2.058561 sec 
有稍微的下降


在 models.inc 新增了物件畫出神奇圈圈
執行時間為 2.561502 sec