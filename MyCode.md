# My Code from my 1040 class
## _Links to other pages_
- [Read Me,](README.md)
- [Simple Way of life,](simple_life.md)
- [Mountians,](Mountianviews.md)
- [My Code,](MyCode.md)
- [Fun Facts](Fun_Facts.md)

        from collections import Counter
        def main():
            input_files = False
            while(input_files == False):
                try:
                    file_name = input('Enter the file name: ')
                    file_handler = open(file_name,"r")
                    lines = file_handler.readlines()
                    file_handler.close()
                except IOError:
                    print(file_name,'could not be opened')
                except ZeroDivisionError:
                    Average= total_count / Count
                    print('This file has no numbers')
                else:
                    print('File Name:',file_name)
                    total=0
                    Average=0
                    total_count=0
                    min_value=9999999
                    max_value=0
                    sort_list = sorted([int(z) for z in lines])
                    Count = len(lines)
                    data = Counter(sort_list)
                    get_mode = dict(data)
                    mode = [k for k, v in get_mode.items() if v == max(list(data.values()))]

                    for x in lines:
                        x=int(x.strip())
                        total= total / Count
                        print(x)
                        if x != '\n':
                            total_count += int(x)
                        if min_value >= x:
                            min_value = x
                        if max_value <= x:
                            max_value = x
                        if Count % 2 == 0:
                            median1 = sort_list[Count//2]
                            median2 = sort_list[Count//2 - 1]
                            median = ( median1 + median2)/2
                        else:
                            median = sort_list[Count//2]
                        if len(mode) == sort_list:
                            get_mode = "No mode found"
                        else:
                            get_mode = mode

                try:
                    Average= total_count / Count
                except ZeroDivisionError:
                    print('This file has no numbers')
                else:
                    Range= max_value - min_value
                    print("\nSum:",total_count)
                    print('\nCount:',Count)
                    print('\nAverage',Average)
                    print('\nMaximum:',max_value)
                    print('\nMinimum:',min_value)
                    print('\nRange:',Range)
                    print('\nMedian:',median)
                    print('\nMode',get_mode)


                another_inputfile = input("\nDo you want to open another file? (y/n): ")
                if (another_inputfile != "y"):
                    do_estimate = True
                    break
        main()
