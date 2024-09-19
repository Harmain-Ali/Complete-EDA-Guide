

<!-- UNIVERSAL PROPERTIES -->

fig_size = (18, 10)
fig_facecolor = '0.93'
fig_fontsize = 20
fig_fontweight = 'bold'
sub_plots_facecolor = '#dbdbdb'
sub_plots_edgecolor = '#E6E6E6'
sub_plots_color = '#d93636'
xylabel_fontsize = 15

ax.minorticks_on()
ax.grid(which='minor', linestyle='solid', linewidth='0.5', color='gray')

<!-- DISTRIBUTION SYNTAX HISTOGRAM -->

fig, axes = plt.subplots(nrows=.., ncols=.., figsize=fig_size, facecolor=fig_facecolor)
plt.suptitle('Distributions of Numerical variables', fontsize=fig_fontsize, fontweight=fig_fonttweight)

columns = []

for col, ax in zip(columns, axes.flatten()):
    ax.set_facecolor(sub_plots_facecolor)
    ax.hist(df[col], bins=20, density=True, edgecolor=sub_plots_edgecolor, color=sub_plots_color)
    ax.set_title(f'Distribution of {col}')

plt.tight_layout()
plt.show()



<!-- BOXPLOT OF NUMERICAL VARIABLES SYNTAX -->

fig, axes = plt.subplots(nrows=.., ncols=.., figsize=fig_size, facecolor=fig_facecolor)
plt.suptitle('Boxplots Numerical variables', fontsize=fig_fontsize, fontweight=fig_fonttweight)

columns = []
for col, ax in zip(columns, axes.flatten()):
    ax.set_facecolor(sub_plots_facecolor)
    ax.grid()
    ax.boxplot(df[col],vert = False, showmeans= True)
    ax.set_title(f'Distribution of {col}')

plt.tight_layout()
plt.show()


<!-- CORRELATION SCATTER PLOT SYNTAX -->

fig, axes = plt.subplots(nrows=.., ncols=.., figsize=fig_size, facecolor=fig_facecolor)
plt.suptitle('correlation of Numerical variables with total', fontsize=fig_fontsize, fontweight=fig_fonttweight)

columns = []
target_var = '..'

for col, ax in zip(columns, axes.flatten()):
    ax.set_facecolor(sub_plots_facecolor)
    ax.scatter(df[target_var],df[col], edgecolor=sub_plots_edgecolor, color=sub_plots_color)
    ax.set_title(f'correlation btween {col} and {target_var}')
    ax.set_xlabel(target_var, fontsize = xylabel_fontsize)
    ax.set_ylabel(col, fontsize = xylabel_fontsize)
    correlation = df[target_var].corr(df[col])
    corr_val = f'r = {correlation:.2f}'
    ax.text(df[target_var].min() * 0.99, df[col].max() * 0.95, corr_val, fontsize=12, color='black', bbox=dict(facecolor='#d9d9d9', edgecolor='#636363', boxstyle='round,pad=0.5'))
  
plt.tight_layout()
plt.show()