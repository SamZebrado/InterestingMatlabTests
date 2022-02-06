% fetching
a = rand(1000); % 100 by 100
t = nan(1000,4);
for ii = 1:1000
clear b;tic;b = a(901:1000);t(ii,1) = toc;
clear b;tic;b = a(901:end);t(ii,2) = toc;
clear b;tic;b = a(end+(-99:-1));t(ii,3) = toc;
clear b;tic;b = a(size(a,1)+(-99:-1));t(ii,4) = toc;
end
plot(t)
ylim([0,1e-5])
legend('without end','end as a point','end involved in computing','compute the end first')