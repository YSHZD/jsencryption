# jsencryption

var arr = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'];
	
	function getKey(){
		var str = "";		
		for(var i=0; i<16; i++){
			var pos = Math.round(Math.random() * (arr.length-1));
			str += arr[pos];
		}
		return str;
	}
	 
    function mixStr(key)
    {
		if(key==null || key ==undefined || key.length!=16)
			throw "error";
        var j = 1;
        for (i = 0; i < 15; i++)
        {
			key=insert_item(key,arr[Math.floor(Math.random()*(arr.length-1))],i + j);
            j += 1;
        }
        key+=arr[Math.floor(Math.random()*(arr.length-1))];
        return key;
    }
    function deMixStr(key)
    {
		if(key==null || key ==undefined || key.length!=32)
			throw "error";
        for (i = 0; i < 15; i++)
        {
			key=remove_item(key,i+1);
        }
        key=remove_item(key,16);
        return key;
    }
	
	function insert_item(str,item,index){
		var newstr="";
		var temp=str.substring(0,index);
		var estr=str.substring(index,str.length);
		
		newstr+=temp+item+estr;
		return newstr;
	}
	
	function remove_item(str,index){
		var newstr="";
		var temp=str.substring(0,index);
		var estr=str.substring(index+1,str.length);
		
		newstr+=temp+estr;
		return newstr;
	}
