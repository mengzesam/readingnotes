sed -i '2d' 

awk -F , 'FNR==1&&FNR!=NR{i=1;while(i in col)print col[i++];delete col}{for(i=1;i<=NF;i++){gsub(/\r/,"",$i);col[i]=col[i] $i ","}}END{i=1;while(i in col) print col[i++]}'  *.txt>tempdata.dat

awk -F , 'FNR==1&&FNR!=NR{i=1;while(i in col)print col[i++];delete col}{for(i=1;i<=NF;i++){gsub(/\r/,"",$i);col[i]=col[i] $i ","}}END{i=1;while(i in col) print col[i++]}'  tempdata.dat>out.dat

rm tempdata.dat