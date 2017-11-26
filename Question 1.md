# Question 1
/**********************************************************/
Question 1
题目：如下为类型CMyString的声明，请为该类型添加赋值运算符函数。
class CMyString
{
public:
	CMyString(char* pData = nullptr);
	CMyString(const CMyString& str);
	~CMyString(void);
private:
	char* m_pData;
}
/********************************************************/
//解法一：
	
	CMyString& CMyString::operator=(const CMyString &str)
	{
	
		if(this == &str)
			return *this;
	
		delete []m_pData;
		m_pData = nullptr;
	
		m_pData = new char[strlen(str.m_pData)+1];
		strcpy(m_pData,str.m_pData);
	
		return *this;
	}
/********************************************************/
//解法二：

	CMyString& CMystring::operator=(const CMyString &str)
	{
		if(this! = &str)
		{
			CMyString strTemp(str);
		
			char* pTemp = strTemp.mpData;
			strTemp.mpData = m_pData;
			m_pData = pTemp;
		}
		return *this;
	}
/********************************************************/
