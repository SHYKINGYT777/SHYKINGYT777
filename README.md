cat > result <<EOF
Alice IT 9.5
Bob CSE 9.2
Charlie ECE 8.9
David IT 9.8
Emma CSE 9.1
Frank IT 9.5
Grace ME 8.7
Hannah IT 9.9
Ivan CSE 9.4
Jack ECE 9.0

awk '$3 == 9.5' result
sort -k3 -nr result | head -n 3
awk '$2 == "IT"' result | sort -k3 -nr
find . -maxdepth 1 -type f | wc -l


tr '\n' ' ' < filename
paste -sd ' ' filename
sed -n '5,10p' filename
awk 'NR>=5 && NR<=10' filename
cat > result <<EOF
Alice IT 9.5
Bob CSE 9.2
Charlie ECE 8.9
David IT 9.8
Emma CSE 9.1
Frank IT 9.5
Grace ME 8.7
Hannah IT 9.9
Ivan CSE 9.4
Jack ECE 9.0
EOF
