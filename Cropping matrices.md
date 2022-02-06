% cropping test
a = rand(100); % 100 by 100
t = nan(1000,4);
for ii = 1:1000
b = a;tic;b(1:3,:) = [];t(ii,1) = toc;
b = a;tic;c = b(4:end,:);t(ii,2) = toc;
b = a;c = zeros(size(b)-[3,0]);tic;c = b(4:end,:);t(ii,3) = toc;
b = a;c = zeros(size(b));tic;c = b(4:end,:);t(ii,4) = toc;
end
plot(t)
ylim([0,1e-5])
legend('deleting','picking up','assigning','rewriting')
mean(t)
[h,p] = ttest2(t(:,3),t(:,4))
[h,p] = ttest2(t(:,1),t(:,4))