# Cplusplus_destructor
解構式能保證釋放記憶體資源後，仍被系統有效利用！(GC機制僅能釋放資源。)

解構式利用補數運算子 ~ 後面加上類別名稱，它與建構式互補，建構式利用 new 運算子在 free store （也稱為 dynamic store 動態空間或是 heap 堆積）自由空間中配置一記憶體空間。

# 建構資源

建構幫助容器成為具有效約束條件且具有邊界檢驗能力存取功能的物件，其中 size() 方法能協助尋訪元素。

        Vec(int i) :elem{new int[i]}, sz{i}

        {
            // 對元素初始化
            for (int a=0; a!=i; ++a) elem[i] = 0;
        }
        
# 解構資源

        ~Vec(){
            delete[] elem;
        }
