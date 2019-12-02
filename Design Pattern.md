
单例模式

单线程：

    class Singleton
    {
    private:
        Singleton() {}
    private:
        static Singleton* instance;
        
    public:
        static Singleton* getInstance()
        {
            if (instance == nullptr)
            {
                instance = new Singleton();
            }
            return instance;
        }
    
    };

多线程：

    class Singleton
    {
    private:
        Singleton() {}
    private:
        static Singleton* instance;
        
    public:
        static Singleton* getInstance()
        {
            if (instance == nullptr)
            {
                Lock();
                if (instance == nullptr)
                    instance = new Singleton();
                UnLock();
            }
            return instance;
        }
    
    };
    
