# laba1_sh
#!/bin/sh

read -p "Введите путь к директории: " directory
if [ ! -d "$directory" ]; then
    echo "Данной папки нет"
    exit 1
fi

cd "$directory" || exit 1

result_file="result.txt"
rm -f "$result_file"
х
find . -type f -name "*.sh" -exec sh {} \; >> "$result_file"

cat "$result_file" | sort -rn >>results.txt
