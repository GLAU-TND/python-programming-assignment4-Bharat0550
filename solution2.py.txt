def fun(nestedDict, Dic, currentKey):
    for key in nestedDict.keys():
        if type(nestedDict[key]) == int:
            Dic[(currentKey+"."+key).strip(".")] = nestedDict[key]
        else:
            Dic = fun(nestedDict[key], Dic, (currentKey+"."+key).strip('.'))
    
    return Dic

def func_dic(nestedDic):
    return fun(nestedDic, dict(), "")

def main():
    nestedDictionary = {
        "key": 3,
        "foo": {
            "a": 5,
            "bar": {
                "baz": 8
            }
        }
    }

    dicten = func_dic(nestedDictionary)
    print(dicten)

if __name__ == "__main__":
    main()
