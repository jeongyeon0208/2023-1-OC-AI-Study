# 1-1
import matplotlib.pyplot as plt

x = [0, 1, 2, 3, 4, 5]
y = [123, 1, 59, 40, 10, 100]

plt.plot(x, y)

plt.show()

#1-2
import matplotlib.pyplot as plt
x = [0, 1, 2, 3, 4, 5]
y = [123, 1, 59, 40, 10, 100]

plt.bar(x, y)

plt.show()

# 1-3
import matplotlib.pyplot as plt
import seaborn as sns

penguin_df = sns.load_dataset("penguins")

sns.scatterplot(x="body_mass", y="bill_length", data=penguin_df)
plt.title("Body Mass vs Bill Length")

plt.show()

# 1-4
import matplotlib.pyplot as plt

x = [0, 1, 2, 3, 4, 5]
y = [123, 1, 59, 40, 10, 100]

fig, ax = plt.subplots(1, 3, figsize=(12,5))

#첫번째 그래프 : line plot
ax[0].plot(x, y, color='blue')
ax[0].set_title('Line Plot', fontsize=14, fontweight='bold', color='gray', pad=12)
ax[0].set_xlabel('X', fontsize=14, fontweight='bold', color='gray', labelpad=12)
ax[0].set_ylabel('Y', fontsize=14, fontweight='bold', color='gray', labelpad=12)

#두번째 그래프 : bar plot
ax[1].bar(x, y, color='lightgray', edgecolor='gray')
ax[1].set_title('Bar Plot', fontsize=14, fontweight='bold', color='gray', pad=12)
ax[1].set_xlabel('X', fontsize=14, fontweight='bold', color='gray', labelpad=12)
ax[1].set_ylabel('Y', fontsize=14, fontweight='bold', color='gray', labelpad=12)

#세번째 그래프 : scatter plot
ax[2].scatter(x, y, color='blue', edgecolor='gray')
ax[2].set_title('Scatter Plot', fontsize=14, fontweight='bold', color='gray', pad=12)
ax[2].set_xlabel('X', fontsize=14, fontweight='bold', color='gray', labelpad=12)
ax[2].set_ylabel('Y', fontsize=14, fontweight='bold', color='gray', labelpad=12)

plt.show()

# 1-5
line plot은 시간이나 연속적인 데이터에서 사용하며, 데이터의 추세를 보여준다.
bar plot: 카테고리 데이터에서 사용하며, 각 카테고리 값의 크기를 비교할 때 유용하다.
Scatter plot: 변수 간 관계를 시각화할 때 사용하며, 변수 간 연관성을 쉽게 파악할 수 있다.
그렇기에 몸무게와 키의 상관관계를 그릴 때에는 bar plot보다는 scatter plot이 적절할 것이며, 주가를 표시할 땐 scatter plot보다는 line plot이 적절할 것이다.

plt는 matplotlib의 pyplot 모듈을 의미하며, 사용이 간편하고 간단한 plot을 그릴 때 유용하다.
fig와 axes는 matplotlib에서 subplot을 그릴 때 사용한다. fig는 전체 subplot을 둘러싸는 객체로, 여러 개의 subplot을 묶을 수 있다.
axes는 실제로 subplot을 그리는 객체로, 각 subplot마다 하나씩 필요다. fig와 axes를 사용하면 subplot의 크기, 배치 등을 더 세밀하게 조절할 수 있다.

# 1-6
import matplotlib.pyplot as plt
import seaborn as sns

penguin_df = sns.load_dataset("penguins")

sns.distplot(penguin_df["body_mass_g"], color="orange", hist_kws={"alpha":0.5}, kde=True, kde_kws={"shade":True})

plt.show()

# 1-7
import matplotlib.pyplot as plt

cars=['AUDI', 'BMW', 'FORD', 'TESLA', 'JAGUAR']
data=[23, 29, 41, 12, 17]
explode = [0, 0, 0.2, 0, 0] # FORD의 explode값은 0.2

fig, ax = plt.subplots(figsize=(6, 6))
ax.pie(data, labels=cars, explode=explode, autopct='%1.1f%%', startangle=90, counterclock=False)

plt.title("Car Sales Distribution", fontsize=16, fontweight='bold')
plt.show()

# 1-8
import matplotlib.pyplot as plt
import seaborn as sns
tips=sns.load_dataset('tips')

sns.boxplot(x='size', y='tip', data=tips)

plt.show()

# 2-1
import matplotlib.pyplot as plt

X = ["Tom", "Amy", "Jim", "Bill", "Pegi"]
Y = [8, 23, 52, 37, 64]

fig, ax = plt.subplots()

#Bar plot
bars = ax.bar(X, Y, color="lightgray", edgecolor="gray")

#Annotation
for bar in bars:
    ax.annotate(str(bar.get_height()), xy=(bar.get_x() + bar.get_width() / 2, bar.get_height() - 4),
                ha="center", color="black", fontsize=14, fontweight="bold")

#Horizontal lines
ax.axhline(y=45, color="blue", linestyle="--")
ax.axhline(y=15, color="red", linestyle="--")

#Fill color for the red line
plt.axhspan(0, 15, facecolor="salmon", alpha=0.3)

#Axis labels
ax.set_xlabel("Names", fontsize=14, fontweight="bold", color="gray", labelpad=12)
ax.set_ylabel("Scores", fontsize=14, fontweight="bold", color="gray", labelpad=12)

#Plot title
ax.set_title("Test Scores", fontsize=16, fontweight="bold")

plt.show()