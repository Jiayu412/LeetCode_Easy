int romanToInt(char* s) {
    char romand[] = {'I', 'V', 'X', 'L', 'C', 'D', 'M'};
    int number[] = {1, 5, 10, 50, 100, 500, 1000};
    int i = 0, j = 0, size = 0, num = 0, prev = 0;
    
    size = sizeof(s);
    int temp[size];
    
    
    for (i = 0; i < size-1; i++){
        for (j = 0; j < 7; j++){
            
            if (*(s+i) == romand[j])
                temp[i] = number[j];    
        }
        if(*(s+i) == romand[0]){
            if(*(s+i+1) == romand[1] || *(s+i+1) == romand[2])
                num = num + temp[i] - romand[0];
        }
        else if(*(s+i) == romand[2]){
            if(*(s+i+1) == romand[3] || *(s+i+1) == romand[4])
                num = num + temp[i] - romand[2];
        }
        else if(*(s+i) == romand[4]){
            if(*(s+i+1) == romand[5] || *(s+i+1) == romand[6])
                num = num + temp[i] - romand[4];
        }
        else
            num = num + temp[i]
               
    }
    
    return num;
}
