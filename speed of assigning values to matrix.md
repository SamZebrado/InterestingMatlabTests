a = magic(5);
b = magic (2)
t = nan(1000,3);
for ii = 1:1000
tic;a(1:2,3:4) = b;t(ii,1) = toc;
tic;a(3:6) = b;t(ii,2) = toc;
tic;a([11,12,16,17]) = b;t(ii,3) = toc;
end
plot(t)
legend 'xy range' 'index range' 'indices list'
ylim([0,1e-5])